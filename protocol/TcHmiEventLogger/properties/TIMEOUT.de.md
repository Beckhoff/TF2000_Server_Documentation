# Standard-Timeout für TwinCAT-EventLogger-Anfragen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiEventLogger.Config::TIMEOUT"` |
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
            "symbol": "TcHmiEventLogger.Config::TIMEOUT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEventLogger.Config::TIMEOUT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEventLogger.Config::TIMEOUT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | timespan |
| Minimum | `PT0.1S` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"PT5S"` |

## JSON-Schema

```json
{
    "configDescription": "DESC_TIMEOUT",
    "default": "PT5S",
    "format": "timespan",
    "formatMinimum": "PT0.1S",
    "type": "string"
}
```
