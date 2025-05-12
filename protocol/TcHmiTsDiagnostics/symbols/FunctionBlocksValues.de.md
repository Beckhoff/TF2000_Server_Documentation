# Get information about the functionblock values of a specific safety project.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiTsDiagnostics.FunctionBlocksValues"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| device | string |
| safetyProject | string |

## Beispiel-Anfrage - WebSocket

Get information about the functionblock values of the safety project from 'Device1' and 'Controller1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiTsDiagnostics.FunctionBlocksValues",
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

Get information about the functionblock values of the safety project from 'Device1' and 'Controller1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiTsDiagnostics.FunctionBlocksValues',
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
            'TcHmiTsDiagnostics.FunctionBlocksValues=' +
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
            "onlineCrc": {
                "type": "number"
            },
            "safetyGroups": {
                "items": {
                    "properties": {
                        "networkList": {
                            "items": {
                                "properties": {
                                    "fbList": {
                                        "items": {
                                            "properties": {
                                                "inPortsList": {
                                                    "$ref": "#/definitions/inPortsListValues"
                                                },
                                                "outPortsList": {
                                                    "$ref": "#/definitions/outPortsListValues"
                                                },
                                                "state": {
                                                    "type": "number"
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
                        },
                        "safetyAliasDevicesList": {
                            "type": "array"
                        },
                        "state": {
                            "type": "number"
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
