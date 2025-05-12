# Reset the 2FA-Secret of the specified user

## General information

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Full symbol path | `"TcHmiUserManagement.Reset2FA"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Reset the 2FA-Secret of the user 'test'
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.Reset2FA",
            "writeValue": "test"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Reset the 2FA-Secret of the user 'test'
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.Reset2FA',
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
            'TcHmiUserManagement.Reset2FA=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "type": "boolean"
    },
    "writeValue": {
        "type": "string"
    }
}
```
