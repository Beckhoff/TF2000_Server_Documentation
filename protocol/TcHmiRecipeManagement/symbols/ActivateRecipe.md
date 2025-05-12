# Write all symbols of the given recipe.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |
| Full symbol path | `"TcHmiRecipeManagement.ActivateRecipe"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| path | string |

## Sample request - WebSocket

List the whole path to the recipe
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiRecipeManagement.ActivateRecipe",
            "writeValue": {
                "path": "testfolder::testRecipe"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

List the whole path to the recipe
```javascript
TcHmi.Server.writeSymbol('TcHmiRecipeManagement.ActivateRecipe',
    {
        "path": "testfolder::testRecipe"
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiRecipeManagement.ActivateRecipe=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "path": {
                "type": "string"
            }
        },
        "required": [
            "path"
        ],
        "type": "object"
    }
}
```
