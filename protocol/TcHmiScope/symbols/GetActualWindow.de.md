# Get Data for a specific ScopeChart. Symbols must be called from the same socket as OpenConnection.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.GetActualWindow"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |

## Beispiel-Anfrage - WebSocket

Get Data for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.GetActualWindow",
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

## Beispiel-Anfrage - JavaScript

Get Data for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.GetActualWindow',
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
            'TcHmiScope.GetActualWindow=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "displayWidth": {
                "format": "timespan",
                "type": "string"
            },
            "liveState": {
                "type": "boolean"
            },
            "redo": {
                "type": "boolean"
            },
            "scopeState": {
                "type": "string"
            },
            "undo": {
                "type": "boolean"
            },
            "xAxisEnd": {
                "format": "date-time",
                "type": "string"
            },
            "xAxisStart": {
                "format": "date-time",
                "type": "string"
            }
        },
        "required": [
            "xAxisStart",
            "xAxisEnd",
            "displayWidth",
            "scopeState",
            "liveState",
            "undo",
            "redo"
        ],
        "type": "object"
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
