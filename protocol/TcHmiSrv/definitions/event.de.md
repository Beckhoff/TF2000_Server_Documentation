# Ereignis

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

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
        "payload": {
            "anyOf": [
                {
                    "$ref": "tchmi:server#/definitions/alarm"
                },
                {
                    "$ref": "tchmi:server#/definitions/message"
                },
                {}
            ],
            "description": "Payload can be alarms, messages or any type of user data."
        },
        "payloadType": {
            "$ref": "tchmi:server#/definitions/eventType"
        },
        "sessionId": {
            "type": "string"
        },
        "timeReceived": {
            "format": "date-time",
            "type": "string"
        }
    },
    "required": [
        "name",
        "domain"
    ],
    "type": "object"
}
```
