# File information

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
