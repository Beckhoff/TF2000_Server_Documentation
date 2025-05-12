# 'None' means that there is no bind user, in which case, the bind request is done with what the user inputs in the login form.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::BIND_USER_AUTHENTICATION_MECHANISM"` |
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
            "symbol": "TcHmiLdap.Config::BIND_USER_AUTHENTICATION_MECHANISM"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::BIND_USER_AUTHENTICATION_MECHANISM', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::BIND_USER_AUTHENTICATION_MECHANISM=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"string"` |
| Implicit access is allowed | Yes |
| Default value | `"None"` |

## Enumeration value

- `"None"`
- `"Anonymous"`
- `"Simple"`
- `"Digest-MD5"`
- `"Kerberos-Credential-Cache"`

## JSON schema

```json
{
    "category": "bindUser",
    "configDescription": "DESC_BIND_USER_AUTHENTICATION_MECHANISM",
    "default": "None",
    "enum": [
        "None",
        "Anonymous",
        "Simple",
        "Digest-MD5",
        "Kerberos-Credential-Cache"
    ],
    "propertyOrder": 7,
    "type": "string"
}
```
