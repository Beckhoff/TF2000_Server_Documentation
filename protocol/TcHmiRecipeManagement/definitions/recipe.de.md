# Ein Rezept basiert auf einem Rezepttyp

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
