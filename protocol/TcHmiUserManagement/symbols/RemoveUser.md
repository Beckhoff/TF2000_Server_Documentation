# Remove a user.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Full symbol path | `"TcHmiUserManagement.RemoveUser"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Remove user `test`.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.RemoveUser",
            "writeValue": "test"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Remove user `test`.
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.RemoveUser',
    "test",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiUserManagement.RemoveUser=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true
    },
    "writeValue": {
        "description": "Name of the user.",
        "type": "string"
    }
}
```
