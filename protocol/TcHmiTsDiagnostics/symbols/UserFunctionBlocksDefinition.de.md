# Get information about the user functionblock structure of a specific safety project.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiTsDiagnostics.UserFunctionBlocksDefinition"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| device | string |
| safetyProject | string |

## Beispiel-Anfrage - WebSocket

Get information about the user functionblock structure of the safety project from 'Device1' and 'Controller1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiTsDiagnostics.UserFunctionBlocksDefinition",
            "writeValue": {
                "device": "Device1",
                "safetyProject": "Controller1"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get information about the user functionblock structure of the safety project from 'Device1' and 'Controller1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiTsDiagnostics.UserFunctionBlocksDefinition',
    {
        "device": "Device1",
        "safetyProject": "Controller1"
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
            'TcHmiTsDiagnostics.UserFunctionBlocksDefinition=' +
            data.response.commands[0].readValue);
    }
);
```

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "readValue": {
        "properties": {
            "offlineCrc": {
                "type": "integer"
            },
            "safetyGroups": {
                "items": {
                    "properties": {
                        "groupName": {
                            "type": "string"
                        },
                        "id": {
                            "type": "string"
                        },
                        "networkList": {
                            "items": {
                                "properties": {
                                    "fbList": {
                                        "items": {
                                            "properties": {
                                                "id": {
                                                    "type": "string"
                                                },
                                                "inPortsList": {
                                                    "$ref": "#/definitions/portsListStructure"
                                                },
                                                "name": {
                                                    "type": "string"
                                                },
                                                "orderId": {
                                                    "type": "integer"
                                                },
                                                "outPortsList": {
                                                    "$ref": "#/definitions/portsListStructure"
                                                },
                                                "posX": {
                                                    "type": "integer"
                                                },
                                                "posY": {
                                                    "type": "integer"
                                                },
                                                "type": {
                                                    "type": "integer"
                                                }
                                            },
                                            "type": "object"
                                        },
                                        "type": "array"
                                    },
                                    "id": {
                                        "type": "string"
                                    },
                                    "name": {
                                        "type": "string"
                                    },
                                    "orderId": {
                                        "type": "integer"
                                    }
                                },
                                "type": "object"
                            },
                            "type": "array"
                        }
                    },
                    "type": "object"
                },
                "type": "array"
            }
        },
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "device": {
                "type": "string"
            },
            "safetyProject": {
                "type": "string"
            }
        },
        "required": [
            "device",
            "safetyProject"
        ],
        "type": "object"
    }
}
```
