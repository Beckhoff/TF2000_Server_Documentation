# Abhängig von der Größe des Verzeichnisses kann die Suche zu lange dauern oder zu viele Ergebnisse liefern. Wenn deaktiviert, werden die Benutzernamen aus der TcHmiSrv-Konfiguration gesammelt.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::USE_LDAP_SEARCH_FOR_LISTUSERS"` |
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
            "symbol": "TcHmiLdap.Config::USE_LDAP_SEARCH_FOR_LISTUSERS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::USE_LDAP_SEARCH_FOR_LISTUSERS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::USE_LDAP_SEARCH_FOR_LISTUSERS=' +
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
    "configDescription": "DESC_USE_LDAP_SEARCH_FOR_LISTUSERS",
    "default": false,
    "propertyOrder": 15,
    "type": "boolean"
}
```
