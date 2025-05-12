# Get list of internal symbols of all extensions.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ListInternalSymbols"` |
| Kategorie | symbols |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

List internal symbols of all extension.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListInternalSymbols"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

List internal symbols of all extension.
```javascript
TcHmi.Server.readSymbol('ListInternalSymbols', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListInternalSymbols=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "symbols",
    "readValue": {
        "function": true,
        "type": "object"
    }
}
```
