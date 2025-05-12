# Enable Two-Factor Authentication (2FA) with Time-Based One-Time Passwords (TOTPs). Users will be required to set up 2FA during their next login.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Full symbol path | `"TcHmiUserManagement.Config::ENABLE_TWO_FACTOR_AUTHENTICATION"` |
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
            "symbol": "TcHmiUserManagement.Config::ENABLE_TWO_FACTOR_AUTHENTICATION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiUserManagement.Config::ENABLE_TWO_FACTOR_AUTHENTICATION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiUserManagement.Config::ENABLE_TWO_FACTOR_AUTHENTICATION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |

## Options

| Value | Label |
| ----- | ----- |
| `0` | Never |
| `1` | Always |
| `2` | Only for remote connections |

## JSON schema

```json
{
    "enum": [
        0,
        1,
        2
    ],
    "options": [
        {
            "label": "ALWAYS_OFF_2FA",
            "value": 0
        },
        {
            "label": "ALWAYS_ON_2FA",
            "value": 1
        },
        {
            "label": "REMOTE_2FA",
            "value": 2
        }
    ],
    "type": "integer"
}
```
