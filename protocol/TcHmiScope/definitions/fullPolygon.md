# fullPolygon

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

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
