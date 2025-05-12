# Lokalisierter Text

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "properties": {
        "Locale": {
            "type": "integer"
        },
        "Text": {
            "type": "string"
        }
    },
    "required": [
        "Locale",
        "Text"
    ],
    "type": "object"
}
```
