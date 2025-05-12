# Prozessdaten (ID)

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

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
