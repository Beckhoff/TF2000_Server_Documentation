# portsListStructure

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
