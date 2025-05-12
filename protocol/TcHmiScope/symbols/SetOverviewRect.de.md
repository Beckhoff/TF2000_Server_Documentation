# Set overview rect for a specific chart. Symbols must be called from the same socket as OpenConnection.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.SetOverviewRect"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |
| xDirection | number |  |
| sizeChanged |  |  |

## Beispiel-Anfrage - WebSocket

Set overview rect for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.SetOverviewRect",
            "writeValue": {
                "controlName": "MyScopeYT Chart",
                "scopeConfig": {
                    "chart": "YT Chart",
                    "name": "ScopeConfig"
                },
                "sizeChanged": {
                    "changedAtBeginning": false,
                    "width": 200
                },
                "xDirection": 100
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Set overview rect for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.SetOverviewRect',
    {
        "controlName": "MyScopeYT Chart",
        "scopeConfig": {
            "chart": "YT Chart",
            "name": "ScopeConfig"
        },
        "sizeChanged": {
            "changedAtBeginning": false,
            "width": 200
        },
        "xDirection": 100
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
            'TcHmiScope.SetOverviewRect=' +
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
            },
            "sizeChanged": {
                "changedAtBeginning": {
                    "type": "boolean"
                },
                "width": {
                    "type": "number"
                }
            },
            "xDirection": {
                "type": "number"
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
