# Starts the record for a specific ScopeChart. Symbols must be called from the same socket as OpenConnection.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.StartRecord"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Starts the record for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.StartRecord",
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

Starts the record for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.StartRecord',
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
            'TcHmiScope.StartRecord=' +
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
        "__SystemAdministrators"
    ],
    "writeValue": {
        "oneOf": [
            {
                "properties": {
                    "controlName": {
                        "description": "ScopeChart Name.",
                        "type": "string"
                    },
                    "recordTime": {
                        "description": "Set a new record time.",
                        "format": "timespan",
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
            },
            {
                "properties": {
                    "configName": {
                        "description": "Name of the config.",
                        "type": "string"
                    },
                    "recordTime": {
                        "description": "Set a new record time.",
                        "format": "timespan",
                        "type": "string"
                    }
                },
                "required": [
                    "configName"
                ],
                "type": "object"
            }
        ]
    }
}
```
