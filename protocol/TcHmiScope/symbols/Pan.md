# Pan in a specific ScopeChart. Symbols must be called from the same socket as OpenConnection.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.Pan"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |
| pan | object |  |

## Sample request - WebSocket

Pan in the ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.Pan",
            "writeValue": {
                "controlName": "MyScopeYT Chart",
                "pan": {
                    "chartIndex": 1,
                    "endPoint": {
                        "x": 100,
                        "y": 100
                    },
                    "mouseMode": "Zoom",
                    "startPoint": {
                        "x": 100,
                        "y": 100
                    }
                },
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

Pan in the ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.Pan',
    {
        "controlName": "MyScopeYT Chart",
        "pan": {
            "chartIndex": 1,
            "endPoint": {
                "x": 100,
                "y": 100
            },
            "mouseMode": "Zoom",
            "startPoint": {
                "x": 100,
                "y": 100
            }
        },
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
            'TcHmiScope.Pan=' +
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
                "description": "ScopeChart Name.",
                "type": "string"
            },
            "pan": {
                "properties": {
                    "chartIndex": {
                        "type": "number"
                    },
                    "endPoint": {
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
                    },
                    "mouseMode": {
                        "type": "string"
                    },
                    "startPoint": {
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
                    "startPoint",
                    "endPoint"
                ],
                "type": "object"
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
            "pan"
        ],
        "type": "object"
    }
}
```
