# Intervall für die Datenkomprimierung.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiPostgresHistorize.Config::compressionScheduleInterval"` |
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
            "symbol": "TcHmiPostgresHistorize.Config::compressionScheduleInterval"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiPostgresHistorize.Config::compressionScheduleInterval', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiPostgresHistorize.Config::compressionScheduleInterval=' +
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
    "configDescription": "descCompressionScheduleInterval",
    "default": "P30D",
    "format": "timespan",
    "formatMinimum": "PT30M",
    "propertyOrder": 4,
    "type": "string"
}
```
