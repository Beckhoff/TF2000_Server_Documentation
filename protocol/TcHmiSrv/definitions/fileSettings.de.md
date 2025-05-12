# Dateieinstellungen

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
        "ACCESS": {
            "allOf": [
                {
                    "$ref": "tchmi:server#/definitions/accessEnum"
                },
                {
                    "default": 3
                }
            ]
        },
        "FILESHTTPHEADERS": {
            "description": "DESC_FILESHTTPHEADERS",
            "format": "multiline",
            "type": "string"
        },
        "HTTPSTATUSCODE": {
            "enum": [
                "",
                "200",
                "201",
                "202",
                "301",
                "302",
                "307",
                "308",
                "401",
                "403",
                "404"
            ],
            "type": "string"
        },
        "LOGINPAGE": {
            "type": "string"
        }
    },
    "type": "object"
}
```
