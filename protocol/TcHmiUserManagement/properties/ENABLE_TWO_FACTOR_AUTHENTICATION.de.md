# Aktiviere Zwei-Faktor-Authentifizierung (2FA) mit zeitbasierten Einmalpasswörtern (TOTPs). Benutzer müssen 2FA bei ihrem nächsten Login einrichten.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.Config::ENABLE_TWO_FACTOR_AUTHENTICATION"` |
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
            "symbol": "TcHmiUserManagement.Config::ENABLE_TWO_FACTOR_AUTHENTICATION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiUserManagement.Config::ENABLE_TWO_FACTOR_AUTHENTICATION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiUserManagement.Config::ENABLE_TWO_FACTOR_AUTHENTICATION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Impliziter Zugriff erlaubt | Ja |

## Optionen

| Wert | Label |
| ---- | ----- |
| `0` | Nie |
| `1` | Immer |
| `2` | Nur bei Remote-Verbindungen |

## JSON-Schema

```json
{
    "enum": [
        0,
        1,
        2
    ],
    "options": [
        {
            "label": "ALWAYS_OFF_2FA",
            "value": 0
        },
        {
            "label": "ALWAYS_ON_2FA",
            "value": 1
        },
        {
            "label": "REMOTE_2FA",
            "value": 2
        }
    ],
    "type": "integer"
}
```
