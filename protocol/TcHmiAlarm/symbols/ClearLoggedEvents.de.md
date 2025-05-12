# Remove the alarms from the event database.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiAlarm"` |
| Vollständiger Symbol-Pfad | `"TcHmiAlarm.ClearLoggedEvents"` |
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
            "symbol": "TcHmiAlarm.ClearLoggedEvents"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiAlarm.ClearLoggedEvents', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiAlarm.ClearLoggedEvents=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true
    }
}
```
