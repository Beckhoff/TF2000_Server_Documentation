# Timing

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
| `0` | Early |
| `1` | Normal |
| `2` | Delayed |

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
            "label": "ENUM_EARLY",
            "propertyOrder": 1,
            "value": 0
        },
        {
            "label": "ENUM_NORMAL",
            "propertyOrder": 2,
            "value": 1
        },
        {
            "label": "ENUM_DELAYED",
            "propertyOrder": 3,
            "value": 2
        }
    ],
    "type": "integer"
}
```
