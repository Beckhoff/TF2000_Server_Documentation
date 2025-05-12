# Ignore everything after the first @ in the username submitted by the user. If you are, for example, using 'userPrincipalName' on Active Directory, you need to disable this setting because the userPrincipalName contains an @.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::IGNORE_DOMAIN_SUFFIX_DURING_LOGIN"` |
| Category | authentication |
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
            "symbol": "TcHmiLdap.Config::IGNORE_DOMAIN_SUFFIX_DURING_LOGIN"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::IGNORE_DOMAIN_SUFFIX_DURING_LOGIN', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::IGNORE_DOMAIN_SUFFIX_DURING_LOGIN=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"boolean"` |
| Implicit access is allowed | Yes |
| Default value | `False` |

## JSON schema

```json
{
    "category": "authentication",
    "configDescription": "DESC_IGNORE_DOMAIN_SUFFIX_DURING_LOGIN",
    "default": false,
    "propertyOrder": 13,
    "type": "boolean"
}
```
