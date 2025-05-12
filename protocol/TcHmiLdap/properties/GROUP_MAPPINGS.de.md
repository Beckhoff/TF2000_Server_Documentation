# HMI-Benutzergruppen basierend auf den Attributen eines LDAP-Benutzers setzen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::GROUP_MAPPINGS"` |
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
            "symbol": "TcHmiLdap.Config::GROUP_MAPPINGS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::GROUP_MAPPINGS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::GROUP_MAPPINGS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
[
    {
        "HMI_GROUP": "__SystemUsers",
        "LDAP_ATTRIBUTE_NAME": "",
        "LDAP_ATTRIBUTE_VALUE": ""
    }
]
```

## JSON-Schema

```json
{
    "category": "integration",
    "configDescription": "DESC_GROUP_MAPPINGS",
    "default": [
        {
            "HMI_GROUP": "__SystemUsers",
            "LDAP_ATTRIBUTE_NAME": "",
            "LDAP_ATTRIBUTE_VALUE": ""
        }
    ],
    "items": {
        "properties": {
            "HMI_GROUP": {
                "optionMethod": {
                    "symbol": "TcHmiSrv.Config::USERGROUPS"
                },
                "propertyOrder": 3,
                "type": "string"
            },
            "LDAP_ATTRIBUTE_NAME": {
                "default": "memberOf",
                "propertyOrder": 1,
                "type": "string"
            },
            "LDAP_ATTRIBUTE_VALUE": {
                "allOf": [
                    {
                        "propertyOrder": 2
                    },
                    {
                        "$ref": "#/definitions/ldapAttributeValue"
                    }
                ]
            }
        },
        "required": [
            "LDAP_ATTRIBUTE_NAME",
            "LDAP_ATTRIBUTE_VALUE",
            "HMI_GROUP"
        ],
        "type": "object"
    },
    "propertyOrder": 18,
    "type": "array"
}
```
