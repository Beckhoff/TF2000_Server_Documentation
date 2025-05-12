# Change channel state for a specific chart. Symbols must be called from the same socket as OpenConnection.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.ChangeChannelState"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| controlName | string | Control Name. |
| scopeConfig | object | Information for scope config. |
| channelId | string |  |
| newState | boolean |  |

## Beispiel-Anfrage - WebSocket

Change channel state for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.ChangeChannelState",
            "writeValue": {
                "channelId": "7ec5d26f-e146-462e-b7bf-c596f418d703",
                "controlName": "MyScopeYT Chart",
                "newState": false,
                "scopeConfig": {
                    "chart": "YT Chart",
                    "name": "ScopeConfig"
                }
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Change channel state for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.ChangeChannelState',
    {
        "channelId": "7ec5d26f-e146-462e-b7bf-c596f418d703",
        "controlName": "MyScopeYT Chart",
        "newState": false,
        "scopeConfig": {
            "chart": "YT Chart",
            "name": "ScopeConfig"
        }
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiScope.ChangeChannelState=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "channelId": {
                "type": "string"
            },
            "controlName": {
                "description": "Control Name.",
                "type": "string"
            },
            "newState": {
                "type": "boolean"
            },
            "scopeConfig": {
                "additionalProperties": false,
                "description": "Information for scope config.",
                "properties": {
                    "chart": {
                        "description": "Chart name out of the scope config.",
                        "type": "string"
                    },
                    "name": {
                        "description": "Name of the scope config.",
                        "type": "string"
                    }
                },
                "required": [
                    "name",
                    "chart"
                ],
                "type": "object"
            }
        },
        "required": [
            "controlName",
            "scopeConfig",
            "channelId",
            "newState"
        ],
        "type": "object"
    }
}
```
