# GZIP compression is used by the server and web clients to improve transfer speed and bandwidth utilization.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::DEFLATECOMPRESSIONLEVEL"` |
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
            "symbol": "TcHmiSrv.Config::DEFLATECOMPRESSIONLEVEL"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFLATECOMPRESSIONLEVEL', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFLATECOMPRESSIONLEVEL=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Minimum | `0` |
| Maximum | `9` |
| Implicit access is allowed | Yes |
| Default value | `5` |

## Options

| Value | Label |
| ----- | ----- |
| `1` | Best speed |
| `5` | Medium |
| `9` | Best size |

## JSON schema

```json
{
    "category": "webserver",
    "default": 5,
    "maximum": 9,
    "minimum": 0,
    "options": [
        {
            "label": "GZIP_BEST_SPEED",
            "value": 1
        },
        {
            "label": "GZIP_MEDIUM",
            "value": 5
        },
        {
            "label": "GZIP_BEST_SIZE",
            "value": 9
        }
    ],
    "type": "integer"
}
```
