# Das Intervall von TimescaleDBs add_compression_policy bestimmt den Zeitpunkt, ab dem die Daten komprimiert werden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiPostgresHistorize.Config::compressAfter"` |
| Sichtbarkeit | AlwaysShow |
| Standardmäßig in jeder Konfiguration enthalten | Nein |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiPostgresHistorize.Config::compressAfter"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiPostgresHistorize.Config::compressAfter', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiPostgresHistorize.Config::compressAfter=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | timespan |
| Minimum | `PT30M` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"P30D"` |

## JSON-Schema

```json
{
    "configDescription": "descCompressAfter",
    "default": "P30D",
    "format": "timespan",
    "formatMinimum": "PT30M",
    "propertyOrder": 3,
    "type": "string"
}
```
