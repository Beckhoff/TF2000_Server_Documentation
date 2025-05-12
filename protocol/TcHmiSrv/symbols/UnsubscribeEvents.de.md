# Terminate an event subscription.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"UnsubscribeEvents"` |
| Kategorie | events |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Close the event subscription with requestId 123.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "UnsubscribeEvents",
            "writeValue": 123
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Close the event subscription with requestId 123.
```javascript
TcHmi.Server.writeSymbol('UnsubscribeEvents',
    123,
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'UnsubscribeEvents=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "events",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "description": "The requestId of a subscription.",
        "type": "integer"
    }
}
```
