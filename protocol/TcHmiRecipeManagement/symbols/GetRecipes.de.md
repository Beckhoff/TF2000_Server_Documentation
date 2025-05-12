# Returns all recipes based on a recipe type

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiRecipeManagement.GetRecipes"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| recipeTypePath | string |

## Beispiel-Anfrage - WebSocket

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

## Beispiel-Anfrage - JavaScript

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

## JSON-Schema

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
