# Wird für die Suche nach Nutzer-Einträgen verwendet. {input} wird durch das ersetzt, was der Benutzer in das Anmeldeformular eingibt. {username_attribute} ist ein Platzhalter, der durch das konfigurierte Nutzernamen-Attribut ersetzt wird.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::USER_FILTER"` |
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
            "symbol": "TcHmiLdap.Config::USER_FILTER"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::USER_FILTER', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::USER_FILTER=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"(&({username_attribute}={input})(objectClass=person))"` |

## Wert des Aufzählungstyps

- `"(&({username_attribute}={input})(objectCategory=person)(objectClass=user))"`
- `"(&({username_attribute}={input})(objectClass=person))"`
- `"(&({username_attribute}={input})(objectClass=inetOrgPerson))"`

## JSON-Schema

```json
{
    "category": "authentication",
    "configDescription": "DESC_USER_FILTER",
    "default": "(&({username_attribute}={input})(objectClass=person))",
    "enum": [
        "(&({username_attribute}={input})(objectCategory=person)(objectClass=user))",
        "(&({username_attribute}={input})(objectClass=person))",
        "(&({username_attribute}={input})(objectClass=inetOrgPerson))"
    ],
    "propertyOrder": 11,
    "type": "string"
}
```
