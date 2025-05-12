# Disable 2FA for the current user

## General information

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Full symbol path | `"TcHmiUserManagement.Disable2FA"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| password | string |
| twoFactorToken | string |

## Sample request - WebSocket

Set the 2FA-Status of the current user to 'enabled'
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.Disable2FA",
            "writeValue": {
                "password": "pwd_123",
                "twoFactorToken": "654321"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Set the 2FA-Status of the current user to 'enabled'
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.Disable2FA',
    {
        "password": "pwd_123",
        "twoFactorToken": "654321"
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
            'TcHmiUserManagement.Disable2FA=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "type": "boolean"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "password": {
                "format": "masked",
                "type": "string"
            },
            "twoFactorToken": {
                "format": "masked",
                "type": "string"
            }
        },
        "required": [
            "password",
            "twoFactorToken"
        ],
        "type": "object"
    }
}
```
