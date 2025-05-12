# Process data (object entry ID)

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "properties": {
        "entryIndex": {
            "type": "string"
        },
        "entrySubIndex": {
            "type": "string"
        },
        "io": {
            "type": "string"
        },
        "objectIndex": {
            "type": "string"
        }
    },
    "required": [
        "io",
        "objectIndex",
        "entryIndex",
        "entrySubIndex"
    ],
    "type": "object"
}
```
