# The full DN of the admin user that is used to search for the DN of the user that is trying to sign in. This setting is ignored if the authentication mechanism is 'Anonymous', 'Kerberos-Credential-Cache', or 'None'.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::BIND_USER_DN"` |
| Category | bindUser |
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
            "symbol": "TcHmiLdap.Config::BIND_USER_DN"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

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

## JSON schema

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
