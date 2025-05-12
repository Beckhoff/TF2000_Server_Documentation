# Ordner für Rezepttypen und/oder weitere Ordner

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
