# Get all uploaded records.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.GetAllUploadedRecords"` |
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
            "symbol": "TcHmiScope.GetAllUploadedRecords"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiScope.GetAllUploadedRecords', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiScope.GetAllUploadedRecords=' +
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
                    "description": "Name of file.",
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
        "__SystemAdministrators"
    ]
}
```
