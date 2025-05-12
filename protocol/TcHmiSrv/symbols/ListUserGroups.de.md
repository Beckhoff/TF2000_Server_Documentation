# Returns the names of all configured user groups.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ListUserGroups"` |
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
            "symbol": "ListUserGroups"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ListUserGroups', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListUserGroups=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true,
        "items": {
            "type": "string"
        },
        "type": "array"
    }
}
```
