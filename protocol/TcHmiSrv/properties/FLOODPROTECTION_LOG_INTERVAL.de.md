# Zeit, die gewartet wird, bevor der nächste 'Anfrage fehlgeschlagen' Log-Eintrag erstellt werden soll.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::FLOODPROTECTION_LOG_INTERVAL"` |
| Kategorie | advanced |
| Sichtbarkeit | HideInEngineering |
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
            "symbol": "TcHmiSrv.Config::FLOODPROTECTION_LOG_INTERVAL"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::FLOODPROTECTION_LOG_INTERVAL', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::FLOODPROTECTION_LOG_INTERVAL=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | timespan |
| Minimum | `PT2S` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"PT1M"` |

## JSON-Schema

```json
{
    "category": "advanced",
    "configDescription": "DESC_FLOODPROTECTION_LOG_INTERVAL",
    "default": "PT1M",
    "format": "timespan",
    "formatMinimum": "PT2S",
    "type": "string",
    "visibility": "HideInEngineering"
}
```
