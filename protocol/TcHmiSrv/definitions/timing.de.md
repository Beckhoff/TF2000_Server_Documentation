# Timing

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `1` |

## Optionen

| Wert | Label |
| ---- | ----- |
| `0` | Früh |
| `1` | Normal |
| `2` | Verzögert |

## JSON-Schema

```json
{
    "default": 1,
    "enum": [
        0,
        1,
        2
    ],
    "options": [
        {
            "label": "ENUM_EARLY",
            "propertyOrder": 1,
            "value": 0
        },
        {
            "label": "ENUM_NORMAL",
            "propertyOrder": 2,
            "value": 1
        },
        {
            "label": "ENUM_DELAYED",
            "propertyOrder": 3,
            "value": 2
        }
    ],
    "type": "integer"
}
```
