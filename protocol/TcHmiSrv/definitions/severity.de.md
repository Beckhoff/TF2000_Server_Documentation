# Severity

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
| `-1` | Diagnose |
| `0` | Ausführlich |
| `1` | Informativ |
| `2` | Warnung |
| `3` | Fehler |
| `4` | Kritisch |

## JSON-Schema

```json
{
    "default": 1,
    "enum": [
        -1,
        0,
        1,
        2,
        3,
        4
    ],
    "options": [
        {
            "label": "ENUM_m1_DIAGNOSTICS",
            "value": -1
        },
        {
            "label": "ENUM_0_VERBOSE",
            "value": 0
        },
        {
            "label": "ENUM_1_INFO",
            "value": 1
        },
        {
            "label": "ENUM_2_WARNING",
            "value": 2
        },
        {
            "label": "ENUM_3_ERROR",
            "value": 3
        },
        {
            "label": "ENUM_4_CRITICAL",
            "value": 4
        }
    ],
    "type": "integer"
}
```
