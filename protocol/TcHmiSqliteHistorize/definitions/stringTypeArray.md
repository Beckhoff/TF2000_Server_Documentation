# Width of the XAxis in milliseconds.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |

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
