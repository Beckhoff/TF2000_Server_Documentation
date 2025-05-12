# Change the password of the current user.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Full symbol path | `"TcHmiUserManagement.ChangePassword"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| currentPassword | string |
| newPassword | string |
| twoFactorToken | string |

## Sample request - WebSocket

Change the password of the current user from '29n3<LrmF),+' to 'VV]Bj7aa]q2)'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.ChangePassword",
            "writeValue": {
                "currentPassword": "29n3<LrmF),+",
                "newPassword": "VV]Bj7aa]q2)",
                "twoFactorToken": "123456"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Change the password of the current user from '29n3<LrmF),+' to 'VV]Bj7aa]q2)'.
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.ChangePassword',
    {
        "currentPassword": "29n3<LrmF),+",
        "newPassword": "VV]Bj7aa]q2)",
        "twoFactorToken": "123456"
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
            'TcHmiUserManagement.ChangePassword=' +
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
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "currentPassword": {
                "format": "masked",
                "type": "string"
            },
            "newPassword": {
                "format": "masked",
                "type": "string"
            },
            "twoFactorToken": {
                "format": "masked",
                "type": "string"
            }
        },
        "type": "object"
    }
}
```
