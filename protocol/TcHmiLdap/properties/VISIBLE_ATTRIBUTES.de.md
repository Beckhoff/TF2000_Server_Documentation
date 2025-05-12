# Die Namen der Attribute, die Benutzer von ihrem LDAP-Verzeichniseintrag abfragen können.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::VISIBLE_ATTRIBUTES"` |
| Kategorie | integration |
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
            "symbol": "TcHmiLdap.Config::VISIBLE_ATTRIBUTES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::VISIBLE_ATTRIBUTES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::VISIBLE_ATTRIBUTES=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Duplikate erlaubt | Ja |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
[]
```

## JSON-Schema

```json
{
    "category": "integration",
    "configDescription": "DESC_VISIBLE_ATTRIBUTES",
    "default": [],
    "items": {
        "minLength": 1,
        "type": "string"
    },
    "propertyOrder": 21,
    "type": "array",
    "uniqueItems": true
}
```
