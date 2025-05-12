# children

## General information

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |

## Schema

|  |  |
| - | - |
| Type | `"array"` |
| Implicit access is allowed | Yes |

## JSON schema

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
