# Stops the record for a specific ScopeChart. Symbols must be called from the same socket as OpenConnection.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.StopRecord"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Stops the record for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.StopRecord",
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

Stops the record for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.StopRecord',
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
            'TcHmiScope.StopRecord=' +
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
                    "deleteFromScopeServer": {
                        "description": "Specifies whether the recording should also be deleted directly on the ScopeServer.",
                        "type": "boolean"
                    }
                },
                "required": [
                    "configName",
                    "deleteFromScopeServer"
                ],
                "type": "object"
            }
        ]
    }
}
```
