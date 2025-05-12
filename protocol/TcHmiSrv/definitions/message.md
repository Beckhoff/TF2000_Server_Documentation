# Message

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "additionalProperties": false,
    "properties": {
        "domain": {
            "type": "string"
        },
        "name": {
            "type": "string"
        },
        "params": {
            "additionalProperties": {},
            "type": "object"
        },
        "severity": {
            "$ref": "tchmi:server#/definitions/severity"
        },
        "timeRaised": {
            "format": "date-time",
            "type": "string"
        }
    },
    "required": [
        "name",
        "domain",
        "severity"
    ],
    "type": "object"
}
```
