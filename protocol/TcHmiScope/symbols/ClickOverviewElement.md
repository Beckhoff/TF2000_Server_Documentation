# Click on overview marker or trigger for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.ClickOverviewElement"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | Control name. |
| scopeConfig | object | Information for scope config. |
| clickPoint | object | The point that was clicked. |

## Sample request - WebSocket

Click on overview marker or trigger for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.ClickOverviewElement",
            "writeValue": {
                "clickPoint": {
                    "x": 100,
                    "y": 100
                },
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

Click on overview marker or trigger for chart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.ClickOverviewElement',
    {
        "clickPoint": {
            "x": 100,
            "y": 100
        },
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
            'TcHmiScope.ClickOverviewElement=' +
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
            "clickPoint": {
                "description": "The point that was clicked.",
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
            "controlName": {
                "description": "Control name.",
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
        "type": "object"
    }
}
```
