# Configure timespan.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |

## Schema

|  |  |
| - | - |
| Enumeration type | `"string"` |
| Format | timespan |
| Implicit access is allowed | Yes |

## Enumeration value

- `"Null"`
- `"First"`
- `"Latest"`

## JSON schema

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
