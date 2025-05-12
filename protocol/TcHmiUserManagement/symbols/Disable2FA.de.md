# Disable 2FA for the current user

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.Disable2FA"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| password | string |
| twoFactorToken | string |

## Beispiel-Anfrage - WebSocket

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

## Beispiel-Anfrage - JavaScript

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
