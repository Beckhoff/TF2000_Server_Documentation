# Localized text

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
