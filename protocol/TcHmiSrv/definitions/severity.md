# Severity

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
| `-1` | Diagnostics |
| `0` | Verbose |
| `1` | Info |
| `2` | Warning |
| `3` | Error |
| `4` | Critical |

## JSON schema

```json
{
    "default": 1,
    "enum": [
        -1,
        0,
        1,
        2,
        3,
        4
    ],
    "options": [
        {
            "label": "ENUM_m1_DIAGNOSTICS",
            "value": -1
        },
        {
            "label": "ENUM_0_VERBOSE",
            "value": 0
        },
        {
            "label": "ENUM_1_INFO",
            "value": 1
        },
        {
            "label": "ENUM_2_WARNING",
            "value": 2
        },
        {
            "label": "ENUM_3_ERROR",
            "value": 3
        },
        {
            "label": "ENUM_4_CRITICAL",
            "value": 4
        }
    ],
    "type": "integer"
}
```
