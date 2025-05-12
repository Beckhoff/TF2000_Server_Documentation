# If there are only a few user accounts, selecting the user account using a list box can simplify the login process.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::USERSELECTTYPE"` |
| Category | security |
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
            "symbol": "TcHmiSrv.Config::USERSELECTTYPE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::USERSELECTTYPE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::USERSELECTTYPE=' +
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
| `0` | List box |
| `1` | Text field |

## JSON schema

```json
{
    "category": "security",
    "default": 0,
    "enum": [
        0,
        1
    ],
    "options": [
        {
            "label": "ENUM_COMBOBOX",
            "value": 0
        },
        {
            "label": "ENUM_TEXTFIELD",
            "value": 1
        }
    ],
    "propertyOrder": 14,
    "type": "integer"
}
```
