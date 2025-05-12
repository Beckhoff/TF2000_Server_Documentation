# Get information about the user functionblock values of a specific safety project.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Full symbol path | `"TcHmiTsDiagnostics.UserFunctionBlocksValues"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| device | string |
| safetyProject | string |

## Sample request - WebSocket

Get information about the user functionblock values of the safety project from 'Device1' and 'Controller1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiTsDiagnostics.UserFunctionBlocksValues",
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

Get information about the user functionblock values of the safety project from 'Device1' and 'Controller1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiTsDiagnostics.UserFunctionBlocksValues',
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
            'TcHmiTsDiagnostics.UserFunctionBlocksValues=' +
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
            "userFbs": {
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
