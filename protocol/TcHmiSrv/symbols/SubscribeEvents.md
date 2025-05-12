# Subscribe to events. If events occur and are allowed by the given filter they will be sent to the websocket that called this method.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"SubscribeEvents"` |
| Category | events |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Subscribe to all events.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "SubscribeEvents",
            "writeValue": 77
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Subscribe to all events.
```javascript
TcHmi.Server.writeSymbol('SubscribeEvents',
    77,
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'SubscribeEvents=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "events",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "description": "The requestId of a subscription.",
        "type": "integer"
    }
}
```
