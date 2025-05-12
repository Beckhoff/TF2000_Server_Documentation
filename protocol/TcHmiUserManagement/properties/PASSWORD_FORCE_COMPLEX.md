# According to GMP rules, a password must contain at least one uppercase character, lowercase character, special character, and numeric character.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Full symbol path | `"TcHmiUserManagement.Config::PASSWORD_FORCE_COMPLEX"` |
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
            "symbol": "TcHmiUserManagement.Config::PASSWORD_FORCE_COMPLEX"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiUserManagement.Config::PASSWORD_FORCE_COMPLEX', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiUserManagement.Config::PASSWORD_FORCE_COMPLEX=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |
| Default value | `0` |

## Options

| Value | Label |
| ----- | ----- |
| `0` | None |
| `1` | GMP rules |

## JSON schema

```json
{
    "default": 0,
    "enum": [
        0,
        1
    ],
    "options": [
        {
            "label": "ENUM_NO_COMPLEXITY_RULES",
            "value": 0
        },
        {
            "label": "ENUM_GMP_COMPLEXITY_RULES",
            "value": 1
        }
    ],
    "type": "integer"
}
```
