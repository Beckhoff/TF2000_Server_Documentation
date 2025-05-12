# Alarm

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
        "alarmState": {
            "$ref": "tchmi:server#/definitions/alarmState"
        },
        "confirmationState": {
            "$ref": "tchmi:server#/definitions/confirmationState"
        },
        "domain": {
            "type": "string"
        },
        "id": {
            "type": "integer"
        },
        "isActive": {
            "$ref": "tchmi:general#/definitions/Boolean"
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
        "timeCleared": {
            "$ref": "tchmi:server#/definitions/nullableDateTime"
        },
        "timeConfirmed": {
            "$ref": "tchmi:server#/definitions/nullableDateTime"
        },
        "timeRaised": {
            "format": "date-time",
            "type": "string"
        }
    },
    "required": [
        "name",
        "domain",
        "confirmationState"
    ],
    "type": "object"
}
```
