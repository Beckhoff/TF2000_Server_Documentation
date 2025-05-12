# Ignoriere alles, was nach dem ersten @ im bei der Anmeldung angegebenen Namen steht. Wenn beispielsweise der 'userPrincipalName' auf Active Directory verwendet wird, muss diese Einstellung deaktiviert werden, da der 'userPrincipalName' ein @ enthält.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::IGNORE_DOMAIN_SUFFIX_DURING_LOGIN"` |
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
            "symbol": "TcHmiLdap.Config::IGNORE_DOMAIN_SUFFIX_DURING_LOGIN"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::IGNORE_DOMAIN_SUFFIX_DURING_LOGIN', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::IGNORE_DOMAIN_SUFFIX_DURING_LOGIN=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"boolean"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `False` |

## JSON-Schema

```json
{
    "category": "authentication",
    "configDescription": "DESC_IGNORE_DOMAIN_SUFFIX_DURING_LOGIN",
    "default": false,
    "propertyOrder": 13,
    "type": "boolean"
}
```
