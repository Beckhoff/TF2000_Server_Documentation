# Attribute used to identify the user.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::USERNAME_ATTRIBUTE"` |
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
            "symbol": "TcHmiLdap.Config::USERNAME_ATTRIBUTE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::USERNAME_ATTRIBUTE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::USERNAME_ATTRIBUTE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"string"` |
| Implicit access is allowed | Yes |
| Default value | `"userPrincipalName"` |

## Enumeration value

- `"userPrincipalName"`
- `"sAMAccountName"`
- `"uid"`
- `"mail"`

## JSON schema

```json
{
    "category": "authentication",
    "configDescription": "DESC_USERNAME_ATTRIBUTE",
    "default": "userPrincipalName",
    "enum": [
        "userPrincipalName",
        "sAMAccountName",
        "uid",
        "mail"
    ],
    "propertyOrder": 12,
    "type": "string"
}
```
