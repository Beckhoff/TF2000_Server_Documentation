# Der vollständige DN des Bind-Nutzers, der für die Suche nach dem DN des Nutzers verwendet wird, der versucht, sich anzumelden. Diese Einstellung wird ignoriert, wenn der Authentifizierungsmechanismus 'Anonymous', 'Kerberos-Credential-Cache' oder 'None' ist.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::BIND_USER_DN"` |
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
            "symbol": "TcHmiLdap.Config::BIND_USER_DN"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::BIND_USER_DN', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::BIND_USER_DN=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "allOf": [
        {
            "category": "bindUser",
            "configDescription": "DESC_BIND_USER_DN",
            "default": "",
            "propertyOrder": 8
        },
        {
            "anyOf": [
                {
                    "const": "",
                    "type": "string"
                },
                {
                    "$ref": "#/definitions/ldapDistinguishedName"
                },
                {
                    "$ref": "#/definitions/ldapAttributeValue"
                }
            ]
        }
    ]
}
```
