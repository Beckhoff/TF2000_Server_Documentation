# Get information about the server.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"GetServerInformation"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Get information about the server.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetServerInformation"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get information about the server.
```javascript
TcHmi.Server.readSymbol('GetServerInformation', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'GetServerInformation=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "type": "object"
    }
}
```
