# Wheel in/out a specific ScopeChart. Symbols must be called from the same socket as OpenConnection.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.Wheel"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |
| wheel | object |  |

## Beispiel-Anfrage - WebSocket

Wheel in/out the ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.Wheel",
            "writeValue": {
                "controlName": "MyScopeYT Chart",
                "scopeConfig": {
                    "chart": "YT Chart",
                    "name": "ScopeConfig"
                },
                "wheel": {
                    "chartIndex": 1,
                    "delta": 100,
                    "mouseMode": "Zoom",
                    "mousePosition": {
                        "x": 100,
                        "y": 100
                    }
                }
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Wheel in/out the ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.Wheel',
    {
        "controlName": "MyScopeYT Chart",
        "scopeConfig": {
            "chart": "YT Chart",
            "name": "ScopeConfig"
        },
        "wheel": {
            "chartIndex": 1,
            "delta": 100,
            "mouseMode": "Zoom",
            "mousePosition": {
                "x": 100,
                "y": 100
            }
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
            'TcHmiScope.Wheel=' +
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
            "wheel": {
                "properties": {
                    "chartIndex": {
                        "type": "number"
                    },
                    "delta": {
                        "type": "number"
                    },
                    "mouseMode": {
                        "type": "string"
                    },
                    "mousePosition": {
                        "properties": {
                            "x": {
                                "type": "number"
                            },
                            "y": {
                                "type": "number"
                            }
                        },
                        "required": [
                            "x",
                            "y"
                        ],
                        "type": "object"
                    }
                },
                "required": [
                    "chartIndex",
                    "mouseMode",
                    "delta",
                    "mousePosition"
                ],
                "type": "object"
            }
        },
        "required": [
            "controlName",
            "scopeConfig",
            "wheel"
        ],
        "type": "object"
    }
}
```
