# Alarm-Zustand

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `0` |

## Optionen

| Wert | Label |
| ---- | ----- |
| `0` | Ausgelöst |
| `1` | Quittiert |
| `2` | Beseitigt |
| `3` | Beseitigt und Quittiert |
| `4` | Ungültig |

## JSON-Schema

```json
{
    "default": 0,
    "enum": [
        0,
        1,
        2,
        3,
        4
    ],
    "options": [
        {
            "label": "ENUM_0_RAISED",
            "value": 0
        },
        {
            "label": "ENUM_1_CONFIRMED",
            "value": 1
        },
        {
            "label": "ENUM_2_CLEARED",
            "value": 2
        },
        {
            "label": "ENUM_3_CLEARED_AND_CONFIRMED",
            "value": 3
        },
        {
            "label": "ENUM_4_INVALID",
            "value": 4
        }
    ],
    "type": "integer"
}
```
