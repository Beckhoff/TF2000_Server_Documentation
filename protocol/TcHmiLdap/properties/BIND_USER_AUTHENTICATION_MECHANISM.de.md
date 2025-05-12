# 'None' bedeutet, dass es keinen Bind-Nutzer gibt. In diesem Fall erfolgt die Bind-Anfrage mit dem, was der Benutzer in das Anmeldeformular eingibt.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::BIND_USER_AUTHENTICATION_MECHANISM"` |
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
            "symbol": "TcHmiLdap.Config::BIND_USER_AUTHENTICATION_MECHANISM"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::BIND_USER_AUTHENTICATION_MECHANISM', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::BIND_USER_AUTHENTICATION_MECHANISM=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"None"` |

## Wert des Aufzählungstyps

- `"None"`
- `"Anonymous"`
- `"Simple"`
- `"Digest-MD5"`
- `"Kerberos-Credential-Cache"`

## JSON-Schema

```json
{
    "category": "bindUser",
    "configDescription": "DESC_BIND_USER_AUTHENTICATION_MECHANISM",
    "default": "None",
    "enum": [
        "None",
        "Anonymous",
        "Simple",
        "Digest-MD5",
        "Kerberos-Credential-Cache"
    ],
    "propertyOrder": 7,
    "type": "string"
}
```
