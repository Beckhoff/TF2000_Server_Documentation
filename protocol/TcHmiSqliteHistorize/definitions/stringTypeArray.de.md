# Breite der X-Achse in Millisekunden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"string"` |
| Format | timespan |
| Impliziter Zugriff erlaubt | Ja |

## Wert des Aufzählungstyps

- `"Null"`
- `"First"`
- `"Latest"`

## JSON-Schema

```json
{
    "configDescription": "descStringTypeArray",
    "oneOf": [
        {
            "description": "descStringTypeArrayTimespan",
            "format": "timespan",
            "type": "string"
        },
        {
            "description": "descStringTypeArrayTimestamp",
            "format": "date-time",
            "type": "string"
        },
        {
            "description": "descStringTypeArrayStartPoint",
            "enum": [
                "Null",
                "First",
                "Latest"
            ],
            "type": "string"
        }
    ]
}
```
