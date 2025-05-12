# Filter

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "items": {
        "oneOf": [
            {
                "additionalProperties": false,
                "configDescription": "descComparator",
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!=",
                            "<",
                            ">",
                            "<=",
                            ">=",
                            "contains",
                            "contains not",
                            "== [ignore case]",
                            "!= [ignore case]",
                            "contains [ignore case]",
                            "contains not [ignore case]"
                        ],
                        "type": "string"
                    },
                    "path": {
                        "type": "string"
                    },
                    "value": {
                        "oneOf": [
                            {
                                "type": "string"
                            },
                            {
                                "type": "number"
                            },
                            {
                                "type": "boolean"
                            },
                            {
                                "type": "null"
                            }
                        ]
                    }
                },
                "required": [
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
                "additionalProperties": false,
                "configDescription": "descLogic",
                "properties": {
                    "logic": {
                        "enum": [
                            "AND",
                            "OR"
                        ],
                        "type": "string"
                    }
                },
                "required": [
                    "logic"
                ],
                "type": "object"
            },
            {
                "$ref": "tchmi:server#/definitions/filter"
            }
        ]
    },
    "type": "array"
}
```
