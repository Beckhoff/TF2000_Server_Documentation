# Attribut, das zur Identifizierung des Benutzers verwendet wird.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::USERNAME_ATTRIBUTE"` |
| Kategorie | authentication |
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
            "symbol": "TcHmiLdap.Config::USERNAME_ATTRIBUTE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::USERNAME_ATTRIBUTE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::USERNAME_ATTRIBUTE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"userPrincipalName"` |

## Wert des Aufzählungstyps

- `"userPrincipalName"`
- `"sAMAccountName"`
- `"uid"`
- `"mail"`

## JSON-Schema

```json
{
    "category": "authentication",
    "configDescription": "DESC_USERNAME_ATTRIBUTE",
    "default": "userPrincipalName",
    "enum": [
        "userPrincipalName",
        "sAMAccountName",
        "uid",
        "mail"
    ],
    "propertyOrder": 12,
    "type": "string"
}
```
