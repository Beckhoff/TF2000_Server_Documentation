# Move a trigger in a chart from the start point to the end point.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.MoveTrigger"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |
| chartIndex | number | Index of chart element. |
| startPoint | position |  |
| endPoint | position |  |

## Beispiel-Anfrage - WebSocket

Move a trigger in a chart from the start point to the end point.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.MoveTrigger",
            "writeValue": {
                "chartIndex": 0,
                "controlName": "MyScopeYT Chart",
                "endPoint": {
                    "x": 100,
                    "y": 100
                },
                "scopeConfig": {
                    "chart": "YT Chart",
                    "name": "ScopeConfig"
                },
                "startPoint": {
                    "x": 100,
                    "y": 100
                }
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Move a trigger in a chart from the start point to the end point.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.MoveTrigger',
    {
        "chartIndex": 0,
        "controlName": "MyScopeYT Chart",
        "endPoint": {
            "x": 100,
            "y": 100
        },
        "scopeConfig": {
            "chart": "YT Chart",
            "name": "ScopeConfig"
        },
        "startPoint": {
            "x": 100,
            "y": 100
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
            'TcHmiScope.MoveTrigger=' +
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
            "chartIndex": {
                "description": "Index of chart element.",
                "type": "number"
            },
            "controlName": {
                "description": "ScopeChart Name.",
                "type": "string"
            },
            "endPoint": {
                "$ref": "#/definitions/position"
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
            "startPoint": {
                "$ref": "#/definitions/position"
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
