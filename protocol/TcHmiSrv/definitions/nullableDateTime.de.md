# Nullable datetime

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## JSON-Schema

```json
{
    "allOf": [
        {
            "oneOf": [
                {
                    "format": "date-time",
                    "type": "string"
                },
                {
                    "type": "null"
                }
            ]
        },
        {
            "description": "descNullableDateTime"
        }
    ]
}
```
