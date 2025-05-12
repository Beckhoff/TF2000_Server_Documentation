# Folder for recipes and/or folders

## General information

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

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
