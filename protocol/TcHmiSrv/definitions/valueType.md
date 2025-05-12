# Value type

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
| `0` | null |
| `1` | boolean |
| `2` | integer |
| `3` | number |
| `4` | string |
| `5` | array |
| `6` | map |
| `7` | object |
| `8` | binary |
| `9` | int64 |
| `10` | date-time |
| `11` | timespan |
| `64` | event |
| `65` | message |
| `66` | alarm |
| `256` | any |

## JSON schema

```json
{
    "default": 0,
    "enum": [
        0,
        1,
        2,
        3,
        4,
        5,
        6,
        7,
        8,
        9,
        10,
        11,
        64,
        65,
        66,
        256
    ],
    "options": [
        {
            "label": "ENUM_VALUETYPE_NULL",
            "value": 0
        },
        {
            "label": "ENUM_VALUETYPE_BOOL",
            "value": 1
        },
        {
            "label": "ENUM_VALUETYPE_INT",
            "value": 2
        },
        {
            "label": "ENUM_VALUETYPE_DOUBLE",
            "value": 3
        },
        {
            "label": "ENUM_VALUETYPE_STRING",
            "value": 4
        },
        {
            "label": "ENUM_VALUETYPE_ARRAY",
            "value": 5
        },
        {
            "label": "ENUM_VALUETYPE_MAP",
            "value": 6
        },
        {
            "label": "ENUM_VALUETYPE_STRUCT",
            "value": 7
        },
        {
            "label": "ENUM_VALUETYPE_BINARY",
            "value": 8
        },
        {
            "label": "ENUM_VALUETYPE_INT64",
            "value": 9
        },
        {
            "label": "ENUM_VALUETYPE_DATETIME",
            "value": 10
        },
        {
            "label": "ENUM_VALUETYPE_TIMESPAN",
            "value": 11
        },
        {
            "label": "ENUM_VALUETYPE_EVENT",
            "value": 64
        },
        {
            "label": "ENUM_VALUETYPE_MESSAGE",
            "value": 65
        },
        {
            "label": "ENUM_VALUETYPE_ALARM",
            "value": 66
        },
        {
            "label": "ENUM_VALUETYPE_ANY",
            "value": 256
        }
    ],
    "type": "integer"
}
```
