# Konfigurationshinweise, die nicht mehr gezeigt werden sollen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::DISABLED_CONFIGURATION_HINTS"` |
| Kategorie | advanced |
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
            "symbol": "TcHmiSrv.Config::DISABLED_CONFIGURATION_HINTS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DISABLED_CONFIGURATION_HINTS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DISABLED_CONFIGURATION_HINTS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Duplikate erlaubt | Ja |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "category": "advanced",
    "items": {
        "type": "string"
    },
    "type": "array",
    "uniqueItems": true
}
```
