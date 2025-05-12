# Get information about the functionblock structure of a specific safety project.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Full symbol path | `"TcHmiTsDiagnostics.FunctionBlocksStructure"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| device | string |
| safetyProject | string |

## Sample request - WebSocket

Get information about the functionblock structure of the safety project from 'Device1' and 'Controller1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiTsDiagnostics.FunctionBlocksStructure",
            "writeValue": {
                "device": "Device1",
                "safetyProject": "Controller1"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get information about the functionblock structure of the safety project from 'Device1' and 'Controller1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiTsDiagnostics.FunctionBlocksStructure',
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
            'TcHmiTsDiagnostics.FunctionBlocksStructure=' +
            data.response.commands[0].readValue);
    }
);
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

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
