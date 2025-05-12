# Check if authentication is required for current endpoint.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"IsAuthRequired"` |
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
            "symbol": "IsAuthRequired"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('IsAuthRequired', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'IsAuthRequired=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true,
        "type": "boolean"
    }
}
```
