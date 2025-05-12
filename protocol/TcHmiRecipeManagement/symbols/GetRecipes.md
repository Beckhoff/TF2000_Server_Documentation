# Returns all recipes based on a recipe type

## General information

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |
| Full symbol path | `"TcHmiRecipeManagement.GetRecipes"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| recipeTypePath | string |

## Sample request - WebSocket

Get all recipes based on a specific recipe type path.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiRecipeManagement.GetRecipes",
            "writeValue": {
                "recipeTypePath": "testfolder::testRecipeType"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get all recipes based on a specific recipe type path.
```javascript
TcHmi.Server.writeSymbol('TcHmiRecipeManagement.GetRecipes',
    {
        "recipeTypePath": "testfolder::testRecipeType"
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
            'TcHmiRecipeManagement.GetRecipes=' +
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
            "recipes": {
                "type": "string"
            }
        },
        "type": "array"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "recipeTypePath": {
                "type": "string"
            }
        },
        "required": [
            "recipeTypePath"
        ],
        "type": "object"
    }
}
```
