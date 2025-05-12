# Log out a session

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ForceLogout"` |
| Kategorie | usersAndSessions |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Log out user `test`
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ForceLogout",
            "writeValue": "test"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Log out user `test`
```javascript
TcHmi.Server.writeSymbol('ForceLogout',
    "test",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'ForceLogout=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "anyOf": [
            {
                "description": "User name. The authentication domain can be specified by using 'Domain::UserName'. If no domain is specified all users with the given name will be logged out.",
                "type": "string"
            },
            {
                "description": "All users",
                "type": "null"
            },
            {
                "properties": {
                    "clientCertificate": {
                        "description": "Thumbprint of the used client certificate",
                        "type": "string"
                    },
                    "clientIp": {
                        "description": "IP address",
                        "type": "string"
                    },
                    "group": {
                        "description": "User group",
                        "type": "string"
                    },
                    "sessionId": {
                        "type": "string"
                    }
                },
                "type": "object"
            }
        ]
    }
}
```
