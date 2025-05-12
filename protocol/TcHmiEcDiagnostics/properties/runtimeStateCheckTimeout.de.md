# Eine konfigurierte Laufzeit wird als nicht erreichbar angesehen, wenn eine Anfrage länger als diese Zeitspanne dauert.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.Config::runtimeStateCheckTimeout"` |
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
            "symbol": "TcHmiEcDiagnostics.Config::runtimeStateCheckTimeout"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEcDiagnostics.Config::runtimeStateCheckTimeout', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEcDiagnostics.Config::runtimeStateCheckTimeout=' +
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
    "type": "string",
    "visibility": "HideInEngineering"
}
```
