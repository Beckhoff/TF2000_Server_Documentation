# Recipes are based on recipe types

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
    "configDescription": "DESC_RECIPE",
    "properties": {
        "comment": {
            "type": "string"
        },
        "recipeTypeName": {
            "type": "string"
        },
        "values": {
            "additionalProperties": {},
            "type": "object"
        }
    },
    "required": [
        "recipeTypeName",
        "values"
    ],
    "type": "object"
}
```
