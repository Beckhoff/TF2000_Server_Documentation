# For example, if the 'email' or 'userPrincipalName' is used for login, this setting can be used to automatically add the domain suffix so that it does not need to be specified at login. The extension does a case-insensitive check to find out if the domain suffix is already present.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::APPEND_DOMAIN_DURING_LOGIN"` |
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
            "symbol": "TcHmiLdap.Config::APPEND_DOMAIN_DURING_LOGIN"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::APPEND_DOMAIN_DURING_LOGIN', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::APPEND_DOMAIN_DURING_LOGIN=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Implicit access is allowed | Yes |
| Default value | `""` |

## JSON schema

```json
{
    "category": "authentication",
    "configDescription": "DESC_APPEND_DOMAIN_DURING_LOGIN",
    "default": "",
    "propertyOrder": 14,
    "type": "string"
}
```
