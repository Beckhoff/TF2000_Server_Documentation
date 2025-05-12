# Get Triggerdata for a specific ScopeChart. Symbols must be called from the same socket as OpenConnection.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.GetTriggerWindow"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |

## Sample request - WebSocket

Get Triggerdata for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.GetTriggerWindow",
            "writeValue": {
                "controlName": "MyScopeYT Chart",
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

## Sample request - JavaScript

Get Triggerdata for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.GetTriggerWindow',
    {
        "controlName": "MyScopeYT Chart",
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
            'TcHmiScope.GetTriggerWindow=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "items": {
            "properties": {
                "comment": {
                    "type": "string"
                },
                "count": {
                    "type": "string"
                },
                "id": {
                    "type": "string"
                },
                "releaseTime": {
                    "format": "date-time",
                    "type": "string"
                },
                "triggerGroup": {
                    "type": "string"
                }
            },
            "required": [
                "id",
                "count",
                "triggerGroup",
                "releaseTime"
            ],
            "type": "object"
        },
        "type": "array"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "controlName": {
                "description": "ScopeChart Name.",
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
            }
        },
        "required": [
            "controlName",
            "scopeConfig"
        ],
        "type": "object"
    }
}
```
