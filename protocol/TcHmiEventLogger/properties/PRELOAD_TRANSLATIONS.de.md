# Reduziert die Anzahl der Netzwerk-Roundtrips für die Lokalisierung und verbessert so die Latenz beim Importieren von Ereignissen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiEventLogger.Config::PRELOAD_TRANSLATIONS"` |
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
            "symbol": "TcHmiEventLogger.Config::PRELOAD_TRANSLATIONS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEventLogger.Config::PRELOAD_TRANSLATIONS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEventLogger.Config::PRELOAD_TRANSLATIONS=' +
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
    "configDescription": "DESC_PRELOAD_TRANSLATIONS",
    "default": false,
    "type": "boolean"
}
```
