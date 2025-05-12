# Check if authentication is required for current endpoint.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"IsAuthRequired"` |
| Category | usersAndSessions |
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
            "symbol": "IsAuthRequired"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('IsAuthRequired', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'IsAuthRequired=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true,
        "type": "boolean"
    }
}
```
