# Gemäß der GMP-Regeln muss ein Passwort Großbuchstaben, Kleinbuchstaben, Sonderzeichen und Zahlen enthalten.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.Config::PASSWORD_FORCE_COMPLEX"` |
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
            "symbol": "TcHmiUserManagement.Config::PASSWORD_FORCE_COMPLEX"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiUserManagement.Config::PASSWORD_FORCE_COMPLEX', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiUserManagement.Config::PASSWORD_FORCE_COMPLEX=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `0` |

## Optionen

| Wert | Label |
| ---- | ----- |
| `0` | Keine |
| `1` | GMP-Regeln |

## JSON-Schema

```json
{
    "default": 0,
    "enum": [
        0,
        1
    ],
    "options": [
        {
            "label": "ENUM_NO_COMPLEXITY_RULES",
            "value": 0
        },
        {
            "label": "ENUM_GMP_COMPLEXITY_RULES",
            "value": 1
        }
    ],
    "type": "integer"
}
```
