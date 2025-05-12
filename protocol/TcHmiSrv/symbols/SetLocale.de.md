# Change the locale of the current session.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"SetLocale"` |
| Kategorie | usersAndSessions |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Set current locale to `en`
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "SetLocale",
            "writeValue": "en"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Set current locale to `en`
```javascript
TcHmi.Server.writeSymbol('SetLocale',
    "en",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'SetLocale=' +
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
        "format": "locale",
        "type": "string"
    }
}
```
