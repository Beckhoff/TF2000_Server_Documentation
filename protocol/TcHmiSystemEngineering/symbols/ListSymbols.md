# List all dynamic symbols.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSystemEngineering"` |
| Full symbol path | `"TcHmiSystemEngineering.ListSymbols"` |
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
            "symbol": "TcHmiSystemEngineering.ListSymbols"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSystemEngineering.ListSymbols', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSystemEngineering.ListSymbols=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {},
        "readOnly": true,
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
