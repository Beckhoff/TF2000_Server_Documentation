# Access level

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |
| Default value | `3` |

## Options

| Value | Label |
| ----- | ----- |
| `0` | None |
| `1` | Read |
| `2` | Write |
| `3` | Read-write |

## JSON schema

```json
{
    "default": 3,
    "enum": [
        0,
        1,
        2,
        3
    ],
    "options": [
        {
            "label": "ENUM_NONE",
            "value": 0
        },
        {
            "label": "ENUM_READ",
            "value": 1
        },
        {
            "label": "ENUM_WRITE",
            "value": 2
        },
        {
            "label": "ENUM_READWRITE",
            "value": 3
        }
    ],
    "type": "integer"
}
```
