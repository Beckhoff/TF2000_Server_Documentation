# Return the currently active user.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"GetCurrentUser"` |
| Kategorie | usersAndSessions |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetCurrentUser"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('GetCurrentUser', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'GetCurrentUser=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true,
        "properties": {
            "autoLoginUser": {
                "type": "boolean"
            },
            "autoLogoff": {
                "format": "timespan",
                "type": "string"
            },
            "clientCertificate": {
                "type": "string"
            },
            "clientIp": {
                "type": "string"
            },
            "configLocale": {
                "type": "string"
            },
            "configTimeFormatLocale": {
                "type": "string"
            },
            "configTimeZone": {
                "type": "string"
            },
            "domain": {
                "type": "string"
            },
            "groups": {
                "items": {
                    "type": "string"
                },
                "type": "array"
            },
            "locale": {
                "type": "string"
            },
            "name": {
                "type": "string"
            },
            "session": {
                "type": "string"
            },
            "timeFormatLocale": {
                "type": "string"
            },
            "timeZone": {
                "type": "string"
            }
        },
        "type": "object"
    }
}
```
