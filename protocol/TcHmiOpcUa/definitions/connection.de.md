# Verbindungseinstellungen

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
