# Subscribe to events. If events occur and are allowed by the given filter they will be sent to the websocket that called this method.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"SubscribeEvents"` |
| Kategorie | events |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Subscribe to all events.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "SubscribeEvents",
            "writeValue": 77
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Subscribe to all events.
```javascript
TcHmi.Server.writeSymbol('SubscribeEvents',
    77,
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'SubscribeEvents=' +
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
