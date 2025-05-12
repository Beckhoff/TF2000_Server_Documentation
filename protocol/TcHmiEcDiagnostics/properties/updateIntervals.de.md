# Minimum time between two asynchronous requests for each request.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.Config::updateIntervals"` |
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
            "symbol": "TcHmiEcDiagnostics.Config::updateIntervals"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEcDiagnostics.Config::updateIntervals', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEcDiagnostics.Config::updateIntervals=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "properties": {
        "MasterList": {
            "default": 1000,
            "description": "Minimum time between two requests in ms.",
            "type": "integer"
        },
        "MasterOnlineInfo": {
            "default": 300,
            "description": "Including frame statistic (sent frames, damaged frames, lost frames, ...) and master state.",
            "type": "integer"
        },
        "ProcessDataValues": {
            "default": 1000,
            "type": "integer"
        },
        "Slaves": {
            "default": 1000,
            "type": "integer"
        },
        "SlavesOnlineInfo": {
            "default": 1000,
            "type": "integer"
        }
    },
    "required": [
        "MasterList",
        "MasterOnlineInfo",
        "Slaves",
        "SlavesOnlineInfo",
        "ProcessDataValues"
    ],
    "type": "object"
}
```
