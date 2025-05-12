# Get information about the project online view structure of a specific safety project.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Full symbol path | `"TcHmiTsDiagnostics.ProjectOnlineViewStructure"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| device | string |
| safetyProject | string |

## Sample request - WebSocket

Get information about the project online view structure of the safety project from 'Device1' and 'Controller1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiTsDiagnostics.ProjectOnlineViewStructure",
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

Get information about the project online view structure of the safety project from 'Device1' and 'Controller1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiTsDiagnostics.ProjectOnlineViewStructure',
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
            'TcHmiTsDiagnostics.ProjectOnlineViewStructure=' +
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
            "Name": {
                "type": "string"
            },
            "children": {
                "$ref": "#/definitions/children"
            }
        },
        "required": [
            "Name",
            "children"
        ],
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
