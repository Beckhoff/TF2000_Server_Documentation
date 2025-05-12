# Write all symbols of the given recipe.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiRecipeManagement.ActivateRecipe"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| path | string |

## Beispiel-Anfrage - WebSocket

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

## Beispiel-Anfrage - JavaScript

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

## JSON-Schema

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
