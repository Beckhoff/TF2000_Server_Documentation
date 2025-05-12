# Change trigger comment for a specific chart. Symbols must be called from the same socket as OpenConnection.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.SetTriggerComment"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | Control name. |
| scopeConfig | object | Information for scope config. |
| triggerId | string | Id for the trigger. |
| newText | string | New text for the trigger. |

## Sample request - WebSocket

Change trigger comment for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.SetTriggerComment",
            "writeValue": {
                "controlName": "MyScopeYT Chart",
                "newText": "New Comment",
                "scopeConfig": {
                    "chart": "YT Chart",
                    "name": "ScopeConfig"
                },
                "triggerId": "7ec5d26f-e146-462e-b7bf-c596f418d703"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Change trigger comment for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.SetTriggerComment',
    {
        "controlName": "MyScopeYT Chart",
        "newText": "New Comment",
        "scopeConfig": {
            "chart": "YT Chart",
            "name": "ScopeConfig"
        },
        "triggerId": "7ec5d26f-e146-462e-b7bf-c596f418d703"
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
            'TcHmiScope.SetTriggerComment=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

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
            "controlName": {
                "description": "Control name.",
                "type": "string"
            },
            "newText": {
                "description": "New text for the trigger.",
                "type": "string"
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
            },
            "triggerId": {
                "description": "Id for the trigger.",
                "type": "string"
            }
        },
        "required": [
            "controlName",
            "scopeConfig",
            "triggerId",
            "newText"
        ],
        "type": "object"
    }
}
```
