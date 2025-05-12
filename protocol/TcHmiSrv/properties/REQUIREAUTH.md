# Authentication should only be disabled on private networks.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::REQUIREAUTH"` |
| Visibility | AlwaysShow |
| Contained in every configuration by default | Yes |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSrv.Config::REQUIREAUTH"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::REQUIREAUTH', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::REQUIREAUTH=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |
| Default value | `2` |

## Options

| Value | Label |
| ----- | ----- |
| `0` | None |
| `1` | Authentication only for remote access |
| `2` | Always authenticate |

## JSON schema

```json
{
    "default": 2,
    "defaultConfigurable": true,
    "enum": [
        0,
        1,
        2
    ],
    "options": [
        {
            "label": "ENUM_NONE",
            "value": 0
        },
        {
            "label": "ENUM_REMOTE",
            "value": 1
        },
        {
            "label": "ENUM_ALWAYS",
            "value": 2
        }
    ],
    "type": "integer"
}
```
