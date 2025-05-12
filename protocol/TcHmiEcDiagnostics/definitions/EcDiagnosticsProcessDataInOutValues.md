# Process data (IN-OUT values)

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "properties": {
        "entries": {
            "items": [
                {
                    "properties": {
                        "error": {
                            "properties": {
                                "code": {
                                    "type": "number"
                                },
                                "message": {
                                    "type": "string"
                                },
                                "reason": {
                                    "type": "string"
                                }
                            },
                            "type": "object"
                        },
                        "forced": {
                            "type": "boolean"
                        },
                        "index": {
                            "type": "string"
                        },
                        "subIndex": {
                            "type": "string"
                        },
                        "value": {}
                    },
                    "required": [
                        "index",
                        "subIndex"
                    ],
                    "type": "object"
                }
            ],
            "type": "array"
        },
        "index": {
            "type": "string"
        }
    },
    "required": [
        "in",
        "out"
    ],
    "type": "object"
}
```
