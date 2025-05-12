# Get a list of the TwinCAT ADS routes.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.ListRoutes"` |
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
            "symbol": "ADS.ListRoutes"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.ListRoutes', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.ListRoutes=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "category": "wrapperFunctions",
    "readValue": {
        "function": true,
        "items": {
            "properties": {
                "label": {
                    "type": "string"
                },
                "name": {
                    "type": "string"
                },
                "value": {
                    "format": "amsnetid",
                    "type": "string"
                }
            },
            "required": [
                "label",
                "name",
                "value"
            ],
            "type": "object"
        },
        "type": "array"
    }
}
```
