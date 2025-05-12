# Einstiegspunkt für LDAP-Suchanfragen. Falls leer, werden die Domain-Komponenten des Hosts verwendet.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::BASE_DN"` |
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
            "symbol": "TcHmiLdap.Config::BASE_DN"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::BASE_DN', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::BASE_DN=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "allOf": [
        {
            "configDescription": "DESC_BASE_DN",
            "default": "",
            "optionMethod": {
                "symbol": "{domain}.ListNamingContexts"
            },
            "propertyOrder": 10
        },
        {
            "anyOf": [
                {
                    "const": "",
                    "type": "string"
                },
                {
                    "$ref": "#/definitions/ldapDistinguishedName"
                }
            ]
        }
    ]
}
```
