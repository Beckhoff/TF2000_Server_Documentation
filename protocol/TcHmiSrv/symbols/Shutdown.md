# Shutdown command.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"Shutdown"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Shutting down the server.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Shutdown"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Shutting down the server.
```javascript
TcHmi.Server.readSymbol('Shutdown', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'Shutdown=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true
    }
}
```
