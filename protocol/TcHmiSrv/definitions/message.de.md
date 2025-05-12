# Nachricht

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
