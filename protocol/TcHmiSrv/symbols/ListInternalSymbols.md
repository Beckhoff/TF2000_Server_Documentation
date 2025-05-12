# Get list of internal symbols of all extensions.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ListInternalSymbols"` |
| Category | symbols |
| Visibility | AlwaysShow |

## Sample request - WebSocket

List internal symbols of all extension.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListInternalSymbols"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

List internal symbols of all extension.
```javascript
TcHmi.Server.readSymbol('ListInternalSymbols', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListInternalSymbols=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "symbols",
    "readValue": {
        "function": true,
        "type": "object"
    }
}
```
