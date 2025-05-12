# Blocked users are not able to log in, even if they logged in successfully in the past.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::BLOCK_USERS"` |
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
            "symbol": "TcHmiLdap.Config::BLOCK_USERS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::BLOCK_USERS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::BLOCK_USERS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## Default value

```json
{
    "LIST": [],
    "USE_WHITELISTING": false
}
```

## JSON schema

```json
{
    "category": "integration",
    "configDescription": "DESC_BLOCK_USERS",
    "default": {
        "LIST": [],
        "USE_WHITELISTING": false
    },
    "properties": {
        "LIST": {
            "default": [],
            "items": {
                "properties": {
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
                    "LDAP_ATTRIBUTE_VALUE"
                ],
                "type": "object"
            },
            "propertyOrder": 3,
            "type": "array"
        },
        "USE_WHITELISTING": {
            "configDescription": "DECS_USE_WHITELISTING",
            "default": false,
            "propertyOrder": 1,
            "type": "boolean"
        },
        "WHITELIST_ACCOUNTS_AFFECTED_BY_GROUP_MAPPINGS": {
            "default": false,
            "description": "DESC_WHITELIST_ACCOUNTS_AFFECTED_BY_GROUP_MAPPINGS",
            "propertyOrder": 2,
            "type": "boolean"
        }
    },
    "propertyOrder": 19,
    "required": [
        "USE_WHITELISTING",
        "WHITELIST_ACCOUNTS_AFFECTED_BY_GROUP_MAPPINGS",
        "LIST"
    ],
    "type": "object"
}
```
