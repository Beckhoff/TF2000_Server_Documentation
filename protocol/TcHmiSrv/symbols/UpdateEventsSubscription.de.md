# Update the subscription to events.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"UpdateEventsSubscription"` |
| Kategorie | events |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Update the existing event subscription with requestId 123.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "filter": "domain == \"ADS\"",
            "symbol": "UpdateEventsSubscription",
            "writeValue": 123
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Update the existing event subscription with requestId 123.
```javascript
TcHmi.Server.request('UpdateEventsSubscription',
    {
        "commands": [
            {
                "commandOptions": [
                    "SendErrorMessage",
                    "SendWriteValue"
                ],
                "filter": "domain == \"ADS\"",
                "symbol": "UpdateEventsSubscription",
                "writeValue": 123
            }
        ],
        "requestType": "ReadWrite"
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'UpdateEventsSubscription=' +
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
