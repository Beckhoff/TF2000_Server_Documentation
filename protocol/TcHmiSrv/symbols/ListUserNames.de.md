# List of usernames.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ListUserNames"` |
| Kategorie | usersAndSessions |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

List all users.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListUserNames"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

List all users.
```javascript
TcHmi.Server.readSymbol('ListUserNames', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListUserNames=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "description": "List of usernames.",
        "function": true,
        "items": {
            "type": "string"
        },
        "type": "array"
    }
}
```
