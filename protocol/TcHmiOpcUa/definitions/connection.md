# Connection settings

## General information

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "additionalProperties": false,
    "properties": {
        "timeout": {
            "default": "PT10S",
            "description": "descTimeout",
            "format": "timespan",
            "formatMaximum": "PT30S",
            "formatMinimum": "PT0.1S",
            "type": "string"
        }
    },
    "required": [
        "timeout"
    ],
    "type": "object"
}
```
