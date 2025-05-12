# Delete configuration.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"DeleteConfiguration"` |
| Category | configurationsAndFilesystem |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Delete the 'cx9020' configuration.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "DeleteConfiguration",
            "writeValue": "cx9020"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Delete the 'cx9020' configuration.
```javascript
TcHmi.Server.writeSymbol('DeleteConfiguration',
    "cx9020",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'DeleteConfiguration=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "configurationsAndFilesystem",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "type": "string"
    }
}
```
