# Returns all recipe types and recipe type folders

## General information

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |
| Full symbol path | `"TcHmiRecipeManagement.ListRecipeTypes"` |
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
            "symbol": "TcHmiRecipeManagement.ListRecipeTypes"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiRecipeManagement.ListRecipeTypes', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiRecipeManagement.ListRecipeTypes=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
