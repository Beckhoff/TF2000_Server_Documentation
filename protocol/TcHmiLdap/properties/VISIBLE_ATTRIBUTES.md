# The names of the attributes that users can query from their LDAP directory entry.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::VISIBLE_ATTRIBUTES"` |
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
            "symbol": "TcHmiLdap.Config::VISIBLE_ATTRIBUTES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::VISIBLE_ATTRIBUTES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::VISIBLE_ATTRIBUTES=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"array"` |
| Unique items | Yes |
| Implicit access is allowed | Yes |

## Default value

```json
[]
```

## JSON schema

```json
{
    "category": "integration",
    "configDescription": "DESC_VISIBLE_ATTRIBUTES",
    "default": [],
    "items": {
        "minLength": 1,
        "type": "string"
    },
    "propertyOrder": 21,
    "type": "array",
    "uniqueItems": true
}
```
