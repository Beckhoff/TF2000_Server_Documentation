# Update the subscription to events.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"UpdateEventsSubscription"` |
| Category | events |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Update the existing event subscription with requestId 123.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "filter": "domain == \"ADS\"",
            "symbol": "UpdateEventsSubscription",
            "writeValue": 123
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Update the existing event subscription with requestId 123.
```javascript
TcHmi.Server.request('UpdateEventsSubscription',
    {
        "commands": [
            {
                "commandOptions": [
                    "SendErrorMessage",
                    "SendWriteValue"
                ],
                "filter": "domain == \"ADS\"",
                "symbol": "UpdateEventsSubscription",
                "writeValue": 123
            }
        ],
        "requestType": "ReadWrite"
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'UpdateEventsSubscription=' +
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
