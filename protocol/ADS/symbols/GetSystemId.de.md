# Get a the local TwinCAT System ID.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.GetSystemId"` |
| Kategorie | wrapperFunctions |
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
            "symbol": "ADS.GetSystemId"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.GetSystemId', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.GetSystemId=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "wrapperFunctions",
    "readValue": {
        "function": true,
        "type": "string"
    }
}
```
