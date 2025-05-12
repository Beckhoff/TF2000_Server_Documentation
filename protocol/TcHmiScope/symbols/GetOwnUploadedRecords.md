# Get uploaded records for the user.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.GetOwnUploadedRecords"` |
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
            "symbol": "TcHmiScope.GetOwnUploadedRecords"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiScope.GetOwnUploadedRecords', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiScope.GetOwnUploadedRecords=' +
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
                "extensionName": {
                    "description": "Name of the extension.",
                    "type": "string"
                },
                "fileName": {
                    "description": "Name of the file.",
                    "type": "string"
                },
                "guid": {
                    "description": "Guid of the uploaded record.",
                    "type": "string"
                },
                "persist": {
                    "description": "Whether a file should be persisted (after shutdown of the extension the file will be deleted).",
                    "type": "boolean"
                },
                "userName": {
                    "description": "Name of the user.",
                    "type": "string"
                }
            },
            "type": "object"
        },
        "type": "array"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
