# children

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "items": {
        "properties": {
            "Name": {
                "type": "string"
            },
            "children": {
                "$ref": "#/definitions/children"
            }
        },
        "required": [
            "Name"
        ],
        "type": "object"
    },
    "type": "array"
}
```
