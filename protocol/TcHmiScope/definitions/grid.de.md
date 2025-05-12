# grid

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "properties": {
        "color": {
            "type": "string"
        },
        "lineWidth": {
            "type": "number"
        },
        "ticks": {
            "type": "number"
        }
    },
    "required": [
        "ticks",
        "color",
        "lineWidth"
    ],
    "type": "object"
}
```
