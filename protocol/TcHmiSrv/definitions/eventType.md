# Event type

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |
| Default value | `1` |

## Options

| Value | Label |
| ----- | ----- |
| `0` | Message |
| `1` | Alarm |
| `2` | Payload |

## JSON schema

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
