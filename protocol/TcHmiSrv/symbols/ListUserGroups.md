# Returns the names of all configured user groups.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ListUserGroups"` |
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
            "symbol": "ListUserGroups"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ListUserGroups', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListUserGroups=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true,
        "items": {
            "type": "string"
        },
        "type": "array"
    }
}
```
