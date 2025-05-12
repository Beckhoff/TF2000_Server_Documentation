# Folder for recipe types and/or folders

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
    "configDescription": "DESC_FOLDER_RECIPETYPE",
    "patternProperties": {
        "^(\\.\\..+|\\..*[^.]|\\..{2,}|(?!\\.\\.|\\.).*)$": {
            "oneOf": [
                {
                    "$ref": "#/definitions/recipeType"
                },
                {
                    "$ref": "#/definitions/folderRecipeType"
                }
            ]
        }
    },
    "type": "object",
    "visibility": "HideInEngineering"
}
```
