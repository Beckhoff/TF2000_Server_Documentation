# Komprimierung beeinflusst sowohl die Speichereffizienz als auch die Abfrageleistung.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiPostgresHistorize.Config::enableCompression"` |
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
            "symbol": "TcHmiPostgresHistorize.Config::enableCompression"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiPostgresHistorize.Config::enableCompression', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiPostgresHistorize.Config::enableCompression=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"boolean"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `False` |

## JSON-Schema

```json
{
    "configDescription": "descCompression",
    "default": false,
    "propertyOrder": 2,
    "type": "boolean"
}
```
