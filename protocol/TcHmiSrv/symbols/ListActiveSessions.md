# Get a list of all active sessions and symbol subscriptions.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ListActiveSessions"` |
| Category | usersAndSessions |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Get a list of all active sessions and symbol subscriptions. Compute the JSON-length of the read-values.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListActiveSessions",
            "writeValue": {
                "readValueJsonLength": true
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get a list of all active sessions and symbol subscriptions. Compute the JSON-length of the read-values.
```javascript
TcHmi.Server.writeSymbol('ListActiveSessions',
    {
        "readValueJsonLength": true
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
            'ListActiveSessions=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true,
        "properties": {
            "clients": {
                "additionalProperties": {
                    "items": {
                        "properties": {
                            "commands": {
                                "items": {
                                    "properties": {
                                        "id": {
                                            "type": "integer"
                                        },
                                        "symbol": {
                                            "type": "string"
                                        }
                                    },
                                    "required": [
                                        "id",
                                        "symbol"
                                    ],
                                    "type": "object"
                                },
                                "type": "array"
                            },
                            "sessionId": {
                                "type": "string"
                            },
                            "userName": {
                                "type": "string"
                            }
                        },
                        "required": [
                            "commands",
                            "sessionId",
                            "userName"
                        ],
                        "type": "object"
                    },
                    "type": "array"
                },
                "type": "object"
            },
            "subscriptions": {
                "additionalProperties": {
                    "properties": {
                        "averageDuration": {
                            "format": "timespan",
                            "type": "string"
                        },
                        "clientCount": {
                            "type": "integer"
                        },
                        "commands": {
                            "items": {
                                "properties": {
                                    "lastSent": {
                                        "format": "date-time",
                                        "type": "string"
                                    },
                                    "readValueJsonLength": {
                                        "minimum": 0,
                                        "type": "integer",
                                        "unit": "byte"
                                    },
                                    "symbol": {
                                        "type": "string"
                                    }
                                },
                                "required": [
                                    "symbol"
                                ],
                                "type": "object"
                            },
                            "type": "array"
                        },
                        "id": {
                            "type": "integer"
                        },
                        "intervalTime": {
                            "type": "integer"
                        },
                        "readValueJsonLength": {
                            "minimum": 0,
                            "type": "integer",
                            "unit": "byte"
                        },
                        "type": {
                            "enum": [
                                "Subscription",
                                "ReadWrite"
                            ],
                            "type": "string"
                        }
                    },
                    "required": [
                        "id",
                        "clientCount",
                        "type",
                        "commands"
                    ],
                    "type": "object"
                },
                "type": "object"
            }
        },
        "type": "object"
    },
    "writeValue": {
        "anyOf": [
            {
                "properties": {
                    "averageDuration": {
                        "default": false,
                        "type": "boolean"
                    },
                    "readValueJsonLength": {
                        "default": false,
                        "type": "boolean"
                    }
                },
                "type": "object"
            },
            {
                "$ref": "tchmi:general#/definitions/VOID"
            }
        ]
    }
}
```
