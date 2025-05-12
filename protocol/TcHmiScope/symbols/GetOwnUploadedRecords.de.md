# Get uploaded records for the user.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.GetOwnUploadedRecords"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

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

## Beispiel-Anfrage - JavaScript

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

## JSON-Schema

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
