# Definiert, ob Cookies bei Cross-Site-Requests mitgesendet werden sollen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::SAMESITE_ATTRIBUTE"` |
| Kategorie | security |
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
            "symbol": "TcHmiSrv.Config::SAMESITE_ATTRIBUTE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::SAMESITE_ATTRIBUTE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::SAMESITE_ATTRIBUTE=' +
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
| `0` | None |
| `1` | Lax |
| `2` | Strict |

## JSON-Schema

```json
{
    "category": "security",
    "configDescription": "DESC_SAMESITE_ATTRIBUTE",
    "default": 2,
    "enum": [
        0,
        1,
        2
    ],
    "options": [
        {
            "label": "ENUM_SAMESITE_NONE",
            "value": 0
        },
        {
            "label": "ENUM_SAMESITE_LAX",
            "value": 1
        },
        {
            "label": "ENUM_SAMESITE_STRICT",
            "value": 2
        }
    ],
    "type": "integer"
}
```
