# Eine konfigurierte Laufzeit wird als nicht erreichbar angesehen, wenn eine Anfrage länger als diese Zeitspanne dauert.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.Config::RUNTIME_STATE_CHECK_TIMEOUT"` |
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
            "symbol": "ADS.Config::RUNTIME_STATE_CHECK_TIMEOUT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::RUNTIME_STATE_CHECK_TIMEOUT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::RUNTIME_STATE_CHECK_TIMEOUT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | timespan |
| Minimum | `PT1S` |
| Maximum | `PT30S` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"PT5S"` |

## JSON-Schema

```json
{
    "default": "PT5S",
    "format": "timespan",
    "formatMaximum": "PT30S",
    "formatMinimum": "PT1S",
    "propertyOrder": 3,
    "type": "string",
    "visibility": "HideInEngineering"
}
```
