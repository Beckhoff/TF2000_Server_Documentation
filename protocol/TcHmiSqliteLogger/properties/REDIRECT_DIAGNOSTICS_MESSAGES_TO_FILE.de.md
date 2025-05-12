# Verringert die Wahrscheinlichkeit, dass eine Flut von Diagnosemeldungen das System überfordert. Besonders nützlich bei der Diagnose von Problemen auf kleineren Geräten. Diese Funktion wird nur auf Windows unterstützt. Server-Neustart erforderlich.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteLogger.Config::REDIRECT_DIAGNOSTICS_MESSAGES_TO_FILE"` |
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
            "symbol": "TcHmiSqliteLogger.Config::REDIRECT_DIAGNOSTICS_MESSAGES_TO_FILE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Config::REDIRECT_DIAGNOSTICS_MESSAGES_TO_FILE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Config::REDIRECT_DIAGNOSTICS_MESSAGES_TO_FILE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"boolean"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `True` |

## JSON-Schema

```json
{
    "configDescription": "DESC_REDIRECT_DIAGNOSTICS_MESSAGES_TO_FILE",
    "default": true,
    "type": "boolean"
}
```
