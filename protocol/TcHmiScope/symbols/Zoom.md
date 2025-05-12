# Zoom into a specific ScopeChart with the zooming start- and endPoint. Symbols must be called from the same socket as OpenConnection.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.Zoom"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |
| zoom | object |  |

## Sample request - WebSocket

Zoom into the ScopeChart named 'MyScopeYT Chart' with the zooming start- and endPoint. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.Zoom",
            "writeValue": {
                "controlName": "MyScopeYT Chart",
                "scopeConfig": {
                    "chart": "YT Chart",
                    "name": "ScopeConfig"
                },
                "zoom": {
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
                }
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Zoom into the ScopeChart named 'MyScopeYT Chart' with the zooming start- and endPoint. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.Zoom',
    {
        "controlName": "MyScopeYT Chart",
        "scopeConfig": {
            "chart": "YT Chart",
            "name": "ScopeConfig"
        },
        "zoom": {
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
            'TcHmiScope.Zoom=' +
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
            "zoom": {
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
            }
        },
        "required": [
            "controlName",
            "scopeConfig",
            "zoom"
        ],
        "type": "object"
    }
}
```
