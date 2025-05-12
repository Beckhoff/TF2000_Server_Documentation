# Get a list of the TwinCAT ADS routes.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.ListRoutes"` |
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
            "symbol": "ADS.ListRoutes"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.ListRoutes', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.ListRoutes=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "wrapperFunctions",
    "readValue": {
        "function": true,
        "items": {
            "properties": {
                "label": {
                    "type": "string"
                },
                "name": {
                    "type": "string"
                },
                "value": {
                    "format": "amsnetid",
                    "type": "string"
                }
            },
            "required": [
                "label",
                "name",
                "value"
            ],
            "type": "object"
        },
        "type": "array"
    }
}
```
