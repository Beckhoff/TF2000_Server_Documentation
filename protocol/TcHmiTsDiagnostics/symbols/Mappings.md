# Get information about the mappings of a specific safety project.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Full symbol path | `"TcHmiTsDiagnostics.Mappings"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| device | string |
| safetyProject | string |

## Sample request - WebSocket

Get information about the mappings of the safety project from 'Device1' and 'Controller1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiTsDiagnostics.Mappings",
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

Get information about the mappings of the safety project from 'Device1' and 'Controller1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiTsDiagnostics.Mappings',
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
            'TcHmiTsDiagnostics.Mappings=' +
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
            "safetyMappings": {
                "items": {
                    "properties": {
                        "localVarName": {
                            "type": "string"
                        },
                        "sourceId": {
                            "type": "string"
                        },
                        "targetId": {
                            "type": "string"
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
