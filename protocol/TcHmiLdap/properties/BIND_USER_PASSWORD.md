# Encrypted before it is stored in the configuration database. Decrypted during a configuration export.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::BIND_USER_PASSWORD"` |
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
            "symbol": "TcHmiLdap.Config::BIND_USER_PASSWORD"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::BIND_USER_PASSWORD', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::BIND_USER_PASSWORD=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | masked |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "category": "bindUser",
    "format": "masked",
    "propertyOrder": 9,
    "type": "string"
}
```
