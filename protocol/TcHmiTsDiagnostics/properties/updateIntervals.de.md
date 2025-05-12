# Minimum time between two asynchronous requests for each request.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiTsDiagnostics.Config::updateIntervals"` |
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
            "symbol": "TcHmiTsDiagnostics.Config::updateIntervals"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiTsDiagnostics.Config::updateIntervals', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiTsDiagnostics.Config::updateIntervals=' +
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
        "OnlineData": {
            "default": 1000,
            "minimum": 1000,
            "type": "integer"
        },
        "Slaves": {
            "default": 1000,
            "type": "integer"
        }
    },
    "required": [
        "MasterList",
        "Slaves",
        "OnlineData"
    ],
    "type": "object"
}
```
