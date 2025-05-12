# Changes will become active after a server restart

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::DISCOVERY"` |
| Category | webserver |
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
            "symbol": "TcHmiSrv.Config::DISCOVERY"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DISCOVERY', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DISCOVERY=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |
| Default value | `1` |

## Options

| Value | Label |
| ----- | ----- |
| `0` | Disabled |
| `1` | Enabled on standard SSDP port (1900) |
| `2` | Enabled on alternative port (1910) |

## JSON schema

```json
{
    "category": "webserver",
    "default": 1,
    "enum": [
        0,
        1,
        2
    ],
    "options": [
        {
            "label": "DISCOVERY_0_DISABLED",
            "value": 0
        },
        {
            "label": "DISCOVERY_1_ENABLED",
            "value": 1
        },
        {
            "label": "DISCOVERY_2_ALTERNATIVE",
            "value": 2
        }
    ],
    "type": "integer"
}
```
