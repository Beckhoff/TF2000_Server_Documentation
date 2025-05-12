# Get the 2FA-Status of the current user or the specified user

## General information

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Full symbol path | `"TcHmiUserManagement.Get2FAStatus"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.Get2FAStatus"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiUserManagement.Get2FAStatus', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiUserManagement.Get2FAStatus=' +
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
| `0` | 2FAEnabled |
| `1` | 2FACanBeEnabled |
| `2` | 2FACannotBeEnabled |
| `3` | 2FACanBeDisabled |
| `4` | 2FANotRequired |

## JSON schema

```json
{
    "readValue": {
        "enum": [
            0,
            1,
            2,
            3,
            4
        ],
        "options": [
            {
                "description": "2FA is enabled.",
                "label": "2FAEnabled",
                "value": 0
            },
            {
                "description": "2FA can be enabled.",
                "label": "2FACanBeEnabled",
                "value": 1
            },
            {
                "description": "2FA cannot be enabled.",
                "label": "2FACannotBeEnabled",
                "value": 2
            },
            {
                "description": "2FA may be disabled.",
                "label": "2FACanBeDisabled",
                "value": 3
            },
            {
                "description": "2FA is enabled but not asked for",
                "label": "2FANotRequired",
                "value": 4
            }
        ],
        "type": "integer"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
