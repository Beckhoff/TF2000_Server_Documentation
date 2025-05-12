# List all mapped symbols.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ListSymbols"` |
| Category | symbols |
| Visibility | AlwaysShow |

## Sample request - WebSocket

List all mapped symbols.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListSymbols"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

List all mapped symbols.
```javascript
TcHmi.Server.readSymbol('ListSymbols', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListSymbols=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "symbols",
    "readValue": {
        "additionalProperties": {
            "$ref": "tchmi:server#/definitions/symbol"
        },
        "function": true,
        "type": "object"
    }
}
```
