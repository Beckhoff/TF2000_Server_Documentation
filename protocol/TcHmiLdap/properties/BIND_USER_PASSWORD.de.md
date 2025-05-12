# Wird vor der Speicherung in der Konfigurationsdatenbank verschlüsselt. Wird beim Export der Konfiguration entschlüsselt.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::BIND_USER_PASSWORD"` |
| Kategorie | bindUser |
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
            "symbol": "TcHmiLdap.Config::BIND_USER_PASSWORD"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::BIND_USER_PASSWORD', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::BIND_USER_PASSWORD=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | masked |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "category": "bindUser",
    "format": "masked",
    "propertyOrder": 9,
    "type": "string"
}
```
