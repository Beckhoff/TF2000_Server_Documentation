# fullPolygon

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
        "polygon": {
            "$ref": "#/definitions/polygon"
        }
    },
    "type": "object"
}
```
