# Wenn beispielsweise die 'email' oder 'userPrincipalName' zur Anmeldung verwendet wird, kann mit dieser Einstellung der Domain-Suffix automatisch ergänzt werden, sodass dieser bei der Anmeldung nicht angegeben werden muss. Es wird eine Prüfung ohne Berücksichtigung der Groß- und Kleinschreibung durchgeführt, um herauszufinden, ob die Domain bereits vorhanden ist.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::APPEND_DOMAIN_DURING_LOGIN"` |
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
            "symbol": "TcHmiLdap.Config::APPEND_DOMAIN_DURING_LOGIN"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::APPEND_DOMAIN_DURING_LOGIN', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::APPEND_DOMAIN_DURING_LOGIN=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `""` |

## JSON-Schema

```json
{
    "category": "authentication",
    "configDescription": "DESC_APPEND_DOMAIN_DURING_LOGIN",
    "default": "",
    "propertyOrder": 14,
    "type": "string"
}
```
