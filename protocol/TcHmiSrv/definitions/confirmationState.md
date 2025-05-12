# Alarm confirmation state

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
| `0` | Not supported |
| `1` | Not required |
| `2` | Waiting for confirmation |
| `3` | Confirmed |
| `4` | Reset |

## JSON schema

```json
{
    "default": 1,
    "enum": [
        0,
        1,
        2,
        3,
        4
    ],
    "options": [
        {
            "label": "ENUM_NOTSUPPORTED",
            "propertyOrder": 2,
            "value": 0
        },
        {
            "label": "ENUM_NOTREQUIRED",
            "propertyOrder": 5,
            "value": 1
        },
        {
            "label": "ENUM_WAIT",
            "propertyOrder": 4,
            "value": 2
        },
        {
            "label": "ENUM_CONFIRMED",
            "propertyOrder": 3,
            "value": 3
        },
        {
            "label": "ENUM_RESET",
            "propertyOrder": 1,
            "value": 4
        }
    ],
    "type": "integer"
}
```
