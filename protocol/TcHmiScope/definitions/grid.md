# grid

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
