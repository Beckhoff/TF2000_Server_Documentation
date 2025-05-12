# Rename a user.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Full symbol path | `"TcHmiUserManagement.RenameUser"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| currentUserName | string | Current name of the user. |
| newUserName | string | The new name of the user. |

## Sample request - WebSocket

Rename user `test` to `tester`.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.RenameUser",
            "writeValue": {
                "currentUserName": "test",
                "newUserName": "tester"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Rename user `test` to `tester`.
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.RenameUser',
    {
        "currentUserName": "test",
        "newUserName": "tester"
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
            'TcHmiUserManagement.RenameUser=' +
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
    "writeValue": {
        "properties": {
            "currentUserName": {
                "description": "Current name of the user.",
                "type": "string"
            },
            "newUserName": {
                "description": "The new name of the user.",
                "type": "string"
            }
        },
        "required": [
            "currentUserName",
            "newUserName"
        ],
        "type": "object"
    }
}
```
