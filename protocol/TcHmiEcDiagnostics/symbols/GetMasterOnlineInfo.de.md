# Get the online information of a specific EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.GetMasterOnlineInfo"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get the online information of the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.GetMasterOnlineInfo",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get the online information of the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.GetMasterOnlineInfo',
    "Device1",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiEcDiagnostics.GetMasterOnlineInfo=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "config": {
                "properties": {
                    "masterNetId": {
                        "type": "string"
                    },
                    "targetNetId": {
                        "type": "string"
                    }
                },
                "type": "object"
            },
            "frames": {
                "properties": {
                    "damaged": {
                        "properties": {
                            "received": {
                                "type": "integer"
                            },
                            "sent": {
                                "type": "integer"
                            }
                        },
                        "required": [
                            "received",
                            "sent"
                        ],
                        "type": "object"
                    },
                    "missed": {
                        "properties": {
                            "acyclic": {
                                "type": "integer"
                            },
                            "cyclic": {
                                "type": "integer"
                            }
                        },
                        "required": [
                            "acyclic",
                            "cyclic"
                        ],
                        "type": "object"
                    },
                    "perSec": {
                        "properties": {
                            "acyclic": {
                                "type": "integer"
                            },
                            "cyclic": {
                                "type": "integer"
                            }
                        },
                        "required": [
                            "acyclic",
                            "cyclic"
                        ],
                        "type": "object"
                    },
                    "total": {
                        "properties": {
                            "acyclic": {
                                "type": "integer"
                            },
                            "cyclic": {
                                "type": "integer"
                            }
                        },
                        "required": [
                            "acyclic",
                            "cyclic"
                        ],
                        "type": "object"
                    }
                },
                "required": [
                    "damaged",
                    "missed",
                    "perSec",
                    "total"
                ],
                "type": "object"
            },
            "stateMachine": {
                "type": "integer"
            },
            "stateMachineRequested": {
                "type": "integer"
            }
        },
        "required": [
            "config",
            "frames",
            "stateMachine"
        ],
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
