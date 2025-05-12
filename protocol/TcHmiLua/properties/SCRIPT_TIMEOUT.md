# Timeout after which the execution of a Lua script is aborted.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLua"` |
| Full symbol path | `"TcHmiLua.Config::SCRIPT_TIMEOUT"` |
| Visibility | AlwaysShow |
| Contained in every configuration by default | No |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiLua.Config::SCRIPT_TIMEOUT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLua.Config::SCRIPT_TIMEOUT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLua.Config::SCRIPT_TIMEOUT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | timespan |
| Minimum | `PT5S` |
| Implicit access is allowed | Yes |
| Default value | `"PT10S"` |

## JSON schema

```json
{
    "configDescription": "DESC_SCRIPT_TIMEOUT",
    "default": "PT10S",
    "format": "timespan",
    "formatMinimum": "PT5S",
    "type": "string"
}
```
