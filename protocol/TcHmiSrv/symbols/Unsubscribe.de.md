# Terminate a subscription.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"Unsubscribe"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Remove subscription with requestId 1
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Unsubscribe",
            "writeValue": 1
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Remove subscription with requestId 1
```javascript
TcHmi.Server.writeSymbol('Unsubscribe',
    1,
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'Unsubscribe=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true
    },
    "writeValue": {
        "description": "The requestId of a subscription.",
        "type": "integer"
    }
}
```
