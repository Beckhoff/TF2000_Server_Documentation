# Authentifizierung sollte nur in privaten Netzwerken deaktiviert werden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::REQUIREAUTH"` |
| Sichtbarkeit | AlwaysShow |
| Standardmäßig in jeder Konfiguration enthalten | Ja |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSrv.Config::REQUIREAUTH"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::REQUIREAUTH', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::REQUIREAUTH=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `2` |

## Optionen

| Wert | Label |
| ---- | ----- |
| `0` | Keine |
| `1` | Authentifizierung nur für Remote-Zugriff |
| `2` | Immer authentifizieren |

## JSON-Schema

```json
{
    "default": 2,
    "defaultConfigurable": true,
    "enum": [
        0,
        1,
        2
    ],
    "options": [
        {
            "label": "ENUM_NONE",
            "value": 0
        },
        {
            "label": "ENUM_REMOTE",
            "value": 1
        },
        {
            "label": "ENUM_ALWAYS",
            "value": 2
        }
    ],
    "type": "integer"
}
```
