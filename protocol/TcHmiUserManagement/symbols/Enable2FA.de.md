# Enable 2FA for the current user and add the secret

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.Enable2FA"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| password | string |
| secret | string |
| twoFactorToken | string |

## Beispiel-Anfrage - WebSocket

Enable 2FA and add a secret for the current
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.Enable2FA",
            "writeValue": {
                "password": "pwd_123",
                "secret": "JBSWY3DPEHPK3PXP",
                "twoFactorToken": "123456"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Enable 2FA and add a secret for the current
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.Enable2FA',
    {
        "password": "pwd_123",
        "secret": "JBSWY3DPEHPK3PXP",
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
            'TcHmiUserManagement.Enable2FA=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

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
                "type": "string"
            },
            "secret": {
                "type": "string"
            },
            "twoFactorToken": {
                "type": "string"
            }
        },
        "required": [
            "password",
            "secret",
            "twoFactorToken"
        ],
        "type": "object"
    }
}
```
