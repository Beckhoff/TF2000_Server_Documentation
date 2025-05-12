# After changing a recipeType updateRecipe is used to update values of all recipes based on this recipeType

## General information

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |
| Full symbol path | `"TcHmiRecipeManagement.UpdateRecipe"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| path | string |

## Sample request - WebSocket

Updates recipe values from recipe testfolder::testRecipe
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiRecipeManagement.UpdateRecipe",
            "writeValue": {
                "path": "testfolder::testRecipe"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Updates recipe values from recipe testfolder::testRecipe
```javascript
TcHmi.Server.writeSymbol('TcHmiRecipeManagement.UpdateRecipe',
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
            'TcHmiRecipeManagement.UpdateRecipe=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "info": {
                "description": "List of updates made",
                "items": {
                    "type": "string"
                },
                "type": "array"
            }
        },
        "type": "object"
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
