# Get a the local TwinCAT System ID.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.GetSystemId"` |
| Category | wrapperFunctions |
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
            "symbol": "ADS.GetSystemId"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.GetSystemId', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.GetSystemId=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "wrapperFunctions",
    "readValue": {
        "function": true,
        "type": "string"
    }
}
```
