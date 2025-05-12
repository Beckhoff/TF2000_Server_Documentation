# List all configurations.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ListConfigurations"` |
| Kategorie | configurationsAndFilesystem |
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
            "symbol": "ListConfigurations"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ListConfigurations', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListConfigurations=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "configurationsAndFilesystem",
    "readValue": {
        "function": true,
        "items": {
            "type": "string"
        },
        "type": "array"
    }
}
```
