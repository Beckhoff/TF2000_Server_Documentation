# Set HMI user groups based on an LDAP user's attributes.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::GROUP_MAPPINGS"` |
| Category | integration |
| Visibility | AlwaysShow |
| Contained in every configuration by default | No |

## Sample request - WebSocket

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

## Sample request - JavaScript

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
| Type | `"array"` |
| Implicit access is allowed | Yes |

## Default value

```json
[
    {
        "HMI_GROUP": "__SystemUsers",
        "LDAP_ATTRIBUTE_NAME": "",
        "LDAP_ATTRIBUTE_VALUE": ""
    }
]
```

## JSON schema

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
