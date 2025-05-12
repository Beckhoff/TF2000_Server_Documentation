# List all mapped symbols.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ListSymbols"` |
| Kategorie | symbols |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

List all mapped symbols.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListSymbols"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

List all mapped symbols.
```javascript
TcHmi.Server.readSymbol('ListSymbols', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListSymbols=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "symbols",
    "readValue": {
        "additionalProperties": {
            "$ref": "tchmi:server#/definitions/symbol"
        },
        "function": true,
        "type": "object"
    }
}
```
