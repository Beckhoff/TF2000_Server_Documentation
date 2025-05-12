# Python Extensions

Python extensions are the simplest way to write TwinCAT HMI Server extensions.

## Prerequisites

Before you begin creating Python extensions for TwinCAT HMI Server,
ensure you have Python 3.12 or later installed on your system and available in `PATH`.

## File Structure

To create a server extension you need the following files:

- `main.py`: The entry point of the extension.
- `requirements.txt`: The dependencies the extension needs to run.
- `{NAME}.Config.json`: The symbol configuration.
- `{NAME}.Schema.json`: (optional) A json schema describing the config settings.

### {NAME}.Config.json

This file describes the symbol configuration of the extensions.
All symbols that should be accessible need to be defined here using a json schema for `readValue` and `writeValue`.

Example `{NAME}.Config.json` that defines a method `LogFunction` and a variable `LastLogEntry`:

```json
{
  "version": "1.0.0.0",
  "configVersion": "1.0.0.0",
  "guid": "19938B42-1C2D-4f41-81B3-DE200A779A82",
  "visibility": "AlwaysShow",
  "symbols": {
    "LastLogEntry": {
      "readValue": {
        "type": "string"
      }
    },
    "LogFunction": {
      "readValue": {
        "type": "array",
        "items": {
          "type": "string"
        },
        "function": true
      },
      "writeValue": {
        "type": "string"
      }
    }
  }
}
```

Note:

- `writeValue` should only be used for `"function": true`, otherwise the readValue schema will be used write access.

### {NAME}.Schema.json

This optional file defines a json schema for your extension's configuration.
The TwinCAT HMI Server will use that schema to automatically generate a web interface.

Example `{NAME}.Schema.json`:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "properties": {
    "maxEntries": {
        "type": "number",
        "default": 1000
    },
    "logLevel": {
        "type": "string",
        "enum": [
            "info",
            "warning",
            "error"
        ],
        "default": "info"
    }
  }
}
```

### main.py

The main.py file is the core of your Python extension.
It handles communication with the TwinCAT HMI Server using a websocket protocol.

Example `main.py`:

```python
import asyncio
from typing import Any, Dict, List
from beckhoff.tchmi.extensionapi import Command, Context, ExtensionHost


class LogExtension(ExtensionHost):
    def __init__(self) -> None:
        self.domain = ''
        self.max_entries = 1000
        self.log_level = 'INFO'
        self.last_log_entry = ''
        super().__init__()

    async def on_config_change(self, context: Context, config: Dict[str, Any]) -> None:
        self.max_entries = config['maxEntries']
        self.log_level = config['logLevel']
        print(f"Config updated: max_entries={self.max_entries}, log_level={self.log_level}")

    async def init(self, domain: str, settings: dict) -> None:
        self.domain = domain
        print(f"Initialized with domain: {domain}")

    async def on_request(self, context: Context, commands: List[Command]) -> None:
        for command in commands:
            if command.symbol == 'LastLogEntry':
                command.readValue = self.last_log_entry
            if command.symbol == 'LogFunction':
                # Add your code here
                self.last_log_entry = command.writeValue


if __name__ == '__main__':
    main = LogExtension()
    asyncio.run(main.run())
```

## Creating And Using Python Extensions

### Creating the extension

Generate the files `main.py`, `TestLogExtension.Schema.json`, `TestLogExtension.Config.json`
and `requirements.txt` as described above in the folder TestLogExtension.

### Adding the extension to the TwinCAT HMI Server

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSrv.Config::EXTENSIONS::PythonLogDomain",
            "writeValue": {
                "ENABLED": true,
                "NAME": "TestLogExtension",
                "PATH": "TestLogExtension"
            }
        }
    ]
}
```

This will call Python method `init` with the parameter `domain` set to `PythonLogDomain`.

### Calling a symbol from the extension

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "PythonLogDomain.LogFunction",
            "writeValue": "Log entry called"
        }
    ]
}
```

This will call the Python method `on_request` with the parameter `List[Command]`:

```json
[
    {
        "symbol": "LogFunction",
        "writeValue": "Log entry called"
    }
]
```

```on_config_change``` is called once initially and with every config change:

```json
{
  "maxEntries": 1000,
  "logLevel": "info"
}
```

## Calling server functions

The API also provides the `execute` method to send server requests:

```python
command = Command('CreateEvent', {
    "name": "FROM_PYTHON",
    "domain": "TcHmiSrv",
    "payloadType": 0,
    "payload": {
        "name": "TEST_MESSAGE",
        "domain": "TcHmiSrv",
        "severity": 1
    }
})
await self.execute([command])
```

`execute` can also be used to read values:

```python
command = Command('Diagnostics')
response: Command = await self.execute([command])
print(response[0].readValue)
```

## Configuration Properties

To change the behavior of the extension host the following settings can be added to the extensions Configuration:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "properties": {
    "extensionHostReloadAutomatically": {
      "type": "boolean",
      "default": false,
      "description": "Controls whether the extension host should automatically reload when changes are detected."
    },
    "extensionHostLogLevel": {
      "type": "string",
      "default": "warning",
      "enum": [
        "debug",
        "info",
        "warning",
        "error"
      ],
      "description": "Controls the log level of the extension host."
    },
    "extensionHostCustomPythonEnvPath": {
      "type": "string",
      "default": "",
      "description": "Specifies a custom Python environment path for the extension host. If no value is provided, a new environment is created in the current working directory."
    },
    "extensionHostDebugPort": {
      "type": "integer",
      "default": 0,
      "description": "Specifies the debug port for the extension host."
    },
    "extensionHostStartupArguments": {
      "type": "string",
      "default": "",
      "description": "Additional startup arguments for the extension host. Use `argparse.parse_known_args()` to parse the arguments in your extension."
    },
    "extensionHostFileSystemWatcherInterval": {
      "type": "string",
      "format": "timespan",
      "default": "PT5S",
      "description": "Specifies the interval for the file system watcher."
    },
    "extensionHostPythonEnvTimeout": {
      "type": "string",
      "format": "timespan",
      "default": "PT5M",
      "description": "Maximum wait time for installing python packages from requirements.txt for python extensions."
    }
  }
}
```

## Troubleshooting

- Check the config page or the log page for detailed error logs.
