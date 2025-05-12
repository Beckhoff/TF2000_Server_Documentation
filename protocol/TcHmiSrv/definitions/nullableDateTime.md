# Nullable datetime

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## JSON schema

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
