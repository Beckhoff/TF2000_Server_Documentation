# Specifies whether cookies should be sent for cross-page requests.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::SAMESITE_ATTRIBUTE"` |
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
            "symbol": "TcHmiSrv.Config::SAMESITE_ATTRIBUTE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::SAMESITE_ATTRIBUTE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::SAMESITE_ATTRIBUTE=' +
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
| `1` | Lax |
| `2` | Strict |

## JSON schema

```json
{
    "category": "security",
    "configDescription": "DESC_SAMESITE_ATTRIBUTE",
    "default": 2,
    "enum": [
        0,
        1,
        2
    ],
    "options": [
        {
            "label": "ENUM_SAMESITE_NONE",
            "value": 0
        },
        {
            "label": "ENUM_SAMESITE_LAX",
            "value": 1
        },
        {
            "label": "ENUM_SAMESITE_STRICT",
            "value": 2
        }
    ],
    "type": "integer"
}
```
