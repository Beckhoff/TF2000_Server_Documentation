# Alarm-Quittierung

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
| `0` | Nicht unterstützt |
| `1` | Nicht erforderlich |
| `2` | Auf Quittierung wartend |
| `3` | Quittiert |
| `4` | Zurückgesetzt |

## JSON-Schema

```json
{
    "default": 1,
    "enum": [
        0,
        1,
        2,
        3,
        4
    ],
    "options": [
        {
            "label": "ENUM_NOTSUPPORTED",
            "propertyOrder": 2,
            "value": 0
        },
        {
            "label": "ENUM_NOTREQUIRED",
            "propertyOrder": 5,
            "value": 1
        },
        {
            "label": "ENUM_WAIT",
            "propertyOrder": 4,
            "value": 2
        },
        {
            "label": "ENUM_CONFIRMED",
            "propertyOrder": 3,
            "value": 3
        },
        {
            "label": "ENUM_RESET",
            "propertyOrder": 1,
            "value": 4
        }
    ],
    "type": "integer"
}
```
