# The most common mechanism is 'Simple'. 'Digest-MD5' is recommended when TLS is unavailable.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::AUTHENTICATION_MECHANISM"` |
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
            "symbol": "TcHmiLdap.Config::AUTHENTICATION_MECHANISM"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::AUTHENTICATION_MECHANISM', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::AUTHENTICATION_MECHANISM=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"string"` |
| Implicit access is allowed | Yes |
| Default value | `"Simple"` |

## Enumeration value

- `"Simple"`
- `"Digest-MD5"`

## JSON schema

```json
{
    "category": "authentication",
    "default": "Simple",
    "enum": [
        "Simple",
        "Digest-MD5"
    ],
    "propertyOrder": 6,
    "type": "string"
}
```
