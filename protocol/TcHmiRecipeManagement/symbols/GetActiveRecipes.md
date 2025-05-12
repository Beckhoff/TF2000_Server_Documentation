# Returns active recipes.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |
| Full symbol path | `"TcHmiRecipeManagement.GetActiveRecipes"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Check whether the 'recipe2' recipe is active.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiRecipeManagement.GetActiveRecipes",
            "writeValue": [
                "recipe2"
            ]
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Check whether the 'recipe2' recipe is active.
```javascript
TcHmi.Server.writeSymbol('TcHmiRecipeManagement.GetActiveRecipes',
    [
        "recipe2"
    ],
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiRecipeManagement.GetActiveRecipes=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "items": {
            "recipe": {
                "type": "string"
            }
        },
        "type": "array"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "anyOf": [
            {
                "items": {
                    "description": "recipe name(s)",
                    "type": "string"
                },
                "type": "array"
            },
            {
                "$ref": "tchmi:general#/definitions/VOID"
            }
        ]
    }
}
```
