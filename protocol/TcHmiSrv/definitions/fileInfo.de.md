# Dateiinformationen

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
    "additionalProperties": true,
    "properties": {
        "access": {
            "$ref": "tchmi:server#/definitions/accessEnum"
        },
        "fileFlags": {
            "items": {
                "enum": [
                    "Directory",
                    "ReadOnly",
                    "UserAccessReadOnly",
                    "VirtualDirectory"
                ],
                "type": "string"
            },
            "type": "array"
        },
        "fileSize": {
            "type": "number",
            "unit": "kilobyte"
        },
        "modificationTime": {
            "type": "string"
        }
    },
    "type": "object"
}
```
