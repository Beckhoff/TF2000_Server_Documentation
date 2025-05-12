# Resize charts in a specific ScopeChart. Symbols must be called from the same socket as OpenConnection.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.ResizeCharts"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |
| resizeOverview | boolean |  |
| charts | array |  |

## Sample request - WebSocket

Resize charts in the ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.ResizeCharts",
            "writeValue": {
                "charts": [
                    {
                        "chartIndex": 0,
                        "height": 100,
                        "width": 100
                    },
                    {
                        "chartIndex": 1,
                        "height": 100,
                        "width": 200
                    }
                ],
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

Resize charts in the ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.ResizeCharts',
    {
        "charts": [
            {
                "chartIndex": 0,
                "height": 100,
                "width": 100
            },
            {
                "chartIndex": 1,
                "height": 100,
                "width": 200
            }
        ],
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
            'TcHmiScope.ResizeCharts=' +
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
            "charts": {
                "items": {
                    "properties": {
                        "chartIndex": {
                            "type": "number"
                        },
                        "height": {
                            "type": "number"
                        },
                        "width": {
                            "type": "number"
                        }
                    },
                    "required": [
                        "width",
                        "chartIndex",
                        "height"
                    ],
                    "type": "object"
                },
                "type": "array"
            },
            "controlName": {
                "description": "ScopeChart Name.",
                "type": "string"
            },
            "resizeOverview": {
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
            "charts"
        ],
        "type": "object"
    }
}
```
