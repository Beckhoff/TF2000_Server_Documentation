# Ordner für Rezepte und/oder weitere Ordner

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "additionalProperties": false,
    "configDescription": "DESC_FOLDER_RECIPE",
    "patternProperties": {
        "^(\\.\\..+|\\..*[^.]|\\..{2,}|(?!\\.\\.|\\.).*)$": {
            "oneOf": [
                {
                    "$ref": "#/definitions/recipe"
                },
                {
                    "$ref": "#/definitions/folderRecipe"
                }
            ]
        }
    },
    "type": "object",
    "visibility": "HideInEngineering"
}
```
