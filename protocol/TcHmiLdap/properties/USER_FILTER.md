# Used to search for the user entry. {input} is a placeholder replaced by what the user inputs in the login form. {username_attribute} is a placeholder replaced by the configured username attribute.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::USER_FILTER"` |
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
            "symbol": "TcHmiLdap.Config::USER_FILTER"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::USER_FILTER', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::USER_FILTER=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"string"` |
| Implicit access is allowed | Yes |
| Default value | `"(&({username_attribute}={input})(objectClass=person))"` |

## Enumeration value

- `"(&({username_attribute}={input})(objectCategory=person)(objectClass=user))"`
- `"(&({username_attribute}={input})(objectClass=person))"`
- `"(&({username_attribute}={input})(objectClass=inetOrgPerson))"`

## JSON schema

```json
{
    "category": "authentication",
    "configDescription": "DESC_USER_FILTER",
    "default": "(&({username_attribute}={input})(objectClass=person))",
    "enum": [
        "(&({username_attribute}={input})(objectCategory=person)(objectClass=user))",
        "(&({username_attribute}={input})(objectClass=person))",
        "(&({username_attribute}={input})(objectClass=inetOrgPerson))"
    ],
    "propertyOrder": 11,
    "type": "string"
}
```
