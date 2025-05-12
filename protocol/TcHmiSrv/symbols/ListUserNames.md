# List of usernames.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ListUserNames"` |
| Category | usersAndSessions |
| Visibility | AlwaysShow |

## Sample request - WebSocket

List all users.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListUserNames"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

List all users.
```javascript
TcHmi.Server.readSymbol('ListUserNames', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListUserNames=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "description": "List of usernames.",
        "function": true,
        "items": {
            "type": "string"
        },
        "type": "array"
    }
}
```
