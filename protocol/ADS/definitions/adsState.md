# ADS state

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |

## Options

| Value | Label |
| ----- | ----- |
| `0` | Invalid |
| `1` | Idle |
| `2` | Reset |
| `3` | Init |
| `4` | Start |
| `5` | Run |
| `6` | Stop |
| `7` | Save configuration |
| `8` | Load configuration |
| `9` | Power failure |
| `10` | Power good |
| `11` | Error |
| `12` | Shutdown |
| `13` | Suspend |
| `14` | Resume |
| `15` | Config |
| `16` | Reconfiguring |
| `17` | Stopping |
| `18` | Incompatible |
| `19` | Exception |

## JSON schema

```json
{
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
        12,
        13,
        14,
        15,
        16,
        17,
        18,
        19
    ],
    "options": [
        {
            "label": "adsStateInvalid",
            "value": 0
        },
        {
            "label": "adsStateIdle",
            "value": 1
        },
        {
            "label": "adsStateReset",
            "value": 2
        },
        {
            "label": "adsStateInit",
            "value": 3
        },
        {
            "label": "adsStateStart",
            "value": 4
        },
        {
            "label": "adsStateRun",
            "value": 5
        },
        {
            "label": "adsStateStop",
            "value": 6
        },
        {
            "label": "adsStateSaveCfg",
            "value": 7
        },
        {
            "label": "adsStateLoadCfg",
            "value": 8
        },
        {
            "label": "adsStatePowerFailure",
            "value": 9
        },
        {
            "label": "adsStatePowerGood",
            "value": 10
        },
        {
            "label": "adsStateError",
            "value": 11
        },
        {
            "label": "adsStateShutdown",
            "value": 12
        },
        {
            "label": "adsStateSuspend",
            "value": 13
        },
        {
            "label": "adsStateResume",
            "value": 14
        },
        {
            "label": "adsStateConfig",
            "value": 15
        },
        {
            "label": "adsStateReconfig",
            "value": 16
        },
        {
            "label": "adsStateStopping",
            "value": 17
        },
        {
            "label": "adsStateIncompatible",
            "value": 18
        },
        {
            "label": "adsStateException",
            "value": 19
        }
    ],
    "type": "integer"
}
```
