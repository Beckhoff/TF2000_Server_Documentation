# Get tooltip at mousePosition for a specific chart. Symbols must be called from the same socket as OpenConnection.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.GetTooltip"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |
| chartIndex | number |  |
| mousePosition | object |  |

## Sample request - WebSocket

Get tooltip at mousePosition for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.GetTooltip",
            "writeValue": {
                "chartIndex": 1,
                "controlName": "MyScopeYT Chart",
                "mousePosition": {
                    "x": 100,
                    "y": 100
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

Get tooltip at mousePosition for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.GetTooltip',
    {
        "chartIndex": 1,
        "controlName": "MyScopeYT Chart",
        "mousePosition": {
            "x": 100,
            "y": 100
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
            'TcHmiScope.GetTooltip=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "chartIndex": {
                "type": "number"
            },
            "displayText": {
                "type": "string"
            },
            "position": {
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
            "timeoutMS": {
                "format": "timespan",
                "type": "string"
            }
        },
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "chartIndex": {
                "type": "number"
            },
            "controlName": {
                "description": "ScopeChart Name.",
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
            "chartIndex",
            "mousePosition"
        ],
        "type": "object"
    }
}
```
