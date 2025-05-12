# Disable a user.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Full symbol path | `"TcHmiUserManagement.DisableUser"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Disable user `test`.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.DisableUser",
            "writeValue": "test"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Disable user `test`.
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.DisableUser',
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
            'TcHmiUserManagement.DisableUser=' +
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
