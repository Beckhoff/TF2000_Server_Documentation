# List all dynamic symbols.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiMdp"` |
| Vollständiger Symbol-Pfad | `"TcHmiMdp.ListSymbols"` |
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
            "symbol": "TcHmiMdp.ListSymbols"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiMdp.ListSymbols', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiMdp.ListSymbols=' +
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
