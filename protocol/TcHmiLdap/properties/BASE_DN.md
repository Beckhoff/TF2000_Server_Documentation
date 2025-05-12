# Entry point for LDAP search requests. If empty, the domain components of the host are used.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::BASE_DN"` |
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
            "symbol": "TcHmiLdap.Config::BASE_DN"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

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

## JSON schema

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
