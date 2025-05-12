# Alarm state

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |
| Default value | `0` |

## Options

| Value | Label |
| ----- | ----- |
| `0` | Raised |
| `1` | Confirmed |
| `2` | Cleared |
| `3` | Cleared and confirmed |
| `4` | Invalid |

## JSON schema

```json
{
    "default": 0,
    "enum": [
        0,
        1,
        2,
        3,
        4
    ],
    "options": [
        {
            "label": "ENUM_0_RAISED",
            "value": 0
        },
        {
            "label": "ENUM_1_CONFIRMED",
            "value": 1
        },
        {
            "label": "ENUM_2_CLEARED",
            "value": 2
        },
        {
            "label": "ENUM_3_CLEARED_AND_CONFIRMED",
            "value": 3
        },
        {
            "label": "ENUM_4_INVALID",
            "value": 4
        }
    ],
    "type": "integer"
}
```
