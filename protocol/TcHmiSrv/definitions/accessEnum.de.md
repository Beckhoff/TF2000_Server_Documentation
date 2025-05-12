# Zugriffsstufe

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `3` |

## Optionen

| Wert | Label |
| ---- | ----- |
| `0` | Keine |
| `1` | Lesen |
| `2` | Schreiben |
| `3` | Lesen und Schreiben |

## JSON-Schema

```json
{
    "default": 3,
    "enum": [
        0,
        1,
        2,
        3
    ],
    "options": [
        {
            "label": "ENUM_NONE",
            "value": 0
        },
        {
            "label": "ENUM_READ",
            "value": 1
        },
        {
            "label": "ENUM_WRITE",
            "value": 2
        },
        {
            "label": "ENUM_READWRITE",
            "value": 3
        }
    ],
    "type": "integer"
}
```
