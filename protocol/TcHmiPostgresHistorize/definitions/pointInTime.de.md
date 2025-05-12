# Zeitspanne wählen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |

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
    "configDescription": "descPointInTime",
    "oneOf": [
        {
            "description": "descPointInTimeTimespan",
            "format": "timespan",
            "type": "string"
        },
        {
            "description": "descPointInTimeTimestamp",
            "format": "date-time",
            "type": "string"
        },
        {
            "description": "descPointInTimeKeywords",
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
