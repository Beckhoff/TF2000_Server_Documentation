# Returns '__SystemUsers', the name of the default user group.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"DefaultUserGroup"` |
| Kategorie | usersAndSessions |
| Sichtbarkeit | HideInEngineering |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "DefaultUserGroup"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('DefaultUserGroup', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'DefaultUserGroup=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "const": "__SystemUsers",
        "function": true,
        "type": "string",
        "visibility": "HideInEngineering"
    }
}
```
