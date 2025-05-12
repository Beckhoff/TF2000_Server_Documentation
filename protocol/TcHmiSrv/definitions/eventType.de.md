# Ereignis-Typ

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
| `0` | Nachricht |
| `1` | Alarm |
| `2` | Nutzlast |

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
            "label": "ENUM_0_MESSAGE",
            "value": 0
        },
        {
            "label": "ENUM_1_ALARM",
            "value": 1
        },
        {
            "label": "ENUM_2_PAYLOAD",
            "value": 2
        }
    ],
    "type": "integer"
}
```
