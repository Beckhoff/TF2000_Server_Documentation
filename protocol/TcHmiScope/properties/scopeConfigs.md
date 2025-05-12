# Scope configurations.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.Config::scopeConfigs"` |
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
            "symbol": "TcHmiScope.Config::scopeConfigs"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiScope.Config::scopeConfigs', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiScope.Config::scopeConfigs=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "additionalProperties": {
        "properties": {
            "AUTOSTART_RECORD": {
                "default": true,
                "type": "boolean"
            },
            "CONFIG_FILE": {
                "format": "base64",
                "type": "string"
            },
            "CONFIG_PATH": {
                "type": "string",
                "visibility": "HideInEngineering"
            },
            "CONFIG_SOURCE": {
                "enum": [
                    "project",
                    "file"
                ],
                "type": "string",
                "visibility": "HideInEngineering"
            }
        },
        "required": [
            "CONFIG_FILE",
            "AUTOSTART_RECORD"
        ],
        "type": "object"
    },
    "configDescription": "DESC_SCOPE_CONFIGS",
    "type": "object"
}
```
