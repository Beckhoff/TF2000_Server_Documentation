# IPv4 and IPv6 endpoints are supported. Only HTTPS endpoints should be enabled for remote access. Use the wildcard addresses '0.0.0.0' and '[::]' to accept remote connections on all network interfaces.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::ENDPOINTS"` |
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
            "symbol": "TcHmiSrv.Config::ENDPOINTS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::ENDPOINTS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::ENDPOINTS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"array"` |
| Unique items | Yes |
| Minimum number of elements | 1 |
| Implicit access is allowed | Yes |

## Default value

```json
[
    "http://127.0.0.1:2010",
    "https://[::]:2020"
]
```

## JSON schema

```json
{
    "category": "webserver",
    "default": [
        "http://127.0.0.1:2010",
        "https://[::]:2020"
    ],
    "items": {
        "type": "string"
    },
    "minItems": 1,
    "type": "array",
    "uniqueItems": true
}
```
