# portsListStructure

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
            "active": {
                "type": "boolean"
            },
            "aliasPortName": {
                "type": "string"
            },
            "id": {
                "type": "string"
            },
            "negated": {
                "type": "boolean"
            },
            "portName": {
                "type": "string"
            },
            "type": {
                "type": "string"
            }
        },
        "type": "object"
    },
    "type": "array"
}
```
