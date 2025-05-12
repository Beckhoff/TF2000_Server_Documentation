# Get a list of common ADS datatypes.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.ListCommonTypes"` |
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
            "symbol": "ADS.ListCommonTypes"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.ListCommonTypes', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.ListCommonTypes=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "items": {
            "properties": {
                "label": {
                    "type": "string"
                },
                "value": {
                    "type": "string"
                }
            },
            "required": [
                "label",
                "value"
            ],
            "type": "object"
        },
        "type": "array"
    }
}
```
