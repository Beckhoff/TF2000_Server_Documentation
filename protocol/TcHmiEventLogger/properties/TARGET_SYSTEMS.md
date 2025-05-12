# Target systems from which events and alarms are collected.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Full symbol path | `"TcHmiEventLogger.Config::TARGET_SYSTEMS"` |
| Visibility | AlwaysShow |
| Contained in every configuration by default | Yes |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEventLogger.Config::TARGET_SYSTEMS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEventLogger.Config::TARGET_SYSTEMS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEventLogger.Config::TARGET_SYSTEMS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## Default value

```json
{
    "Local": {
        "ADDRESS": "127.0.0.1.1.1",
        "ENABLED": true
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "configDescription": "DESC_TARGET_SYSTEM",
        "properties": {
            "ADDRESS": {
                "allOf": [
                    {
                        "$ref": "tchmi:server#/definitions/adsRoute"
                    },
                    {
                        "configDescription": "DESC_ADS_ROUTE"
                    }
                ]
            },
            "ENABLED": {
                "default": true,
                "type": "boolean"
            }
        },
        "required": [
            "ADDRESS",
            "ENABLED"
        ],
        "type": "object"
    },
    "configDescription": "DESC_TARGET_SYSTEMS",
    "default": {
        "Local": {
            "ADDRESS": "127.0.0.1.1.1",
            "ENABLED": true
        }
    },
    "defaultConfigurable": true,
    "type": "object"
}
```
