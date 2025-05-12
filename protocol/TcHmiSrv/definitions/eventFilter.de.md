# Ereignis-Filter

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
        "anyOf": [
            {
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!=",
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
                        "enum": [
                            "domain",
                            "sourceDomain",
                            "name",
                            "text",
                            "sessionId"
                        ],
                        "type": "string"
                    },
                    "value": {
                        "type": "string"
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!=",
                            "<",
                            ">",
                            "<=",
                            ">="
                        ],
                        "type": "string"
                    },
                    "path": {
                        "enum": [
                            "id"
                        ],
                        "type": "string"
                    },
                    "value": {
                        "type": "number"
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!=",
                            "<",
                            ">",
                            "<=",
                            ">="
                        ],
                        "type": "string"
                    },
                    "path": {
                        "enum": [
                            "timeRaised"
                        ],
                        "type": "string"
                    },
                    "value": {
                        "format": "date-time",
                        "type": "string"
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!=",
                            "<",
                            ">",
                            "<=",
                            ">="
                        ],
                        "type": "string"
                    },
                    "path": {
                        "enum": [
                            "timeCleared",
                            "timeConfirmed"
                        ],
                        "type": "string"
                    },
                    "value": {
                        "$ref": "tchmi:server#/definitions/nullableDateTime"
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!=",
                            "<",
                            ">",
                            "<=",
                            ">="
                        ],
                        "type": "string"
                    },
                    "path": {
                        "enum": [
                            "type"
                        ],
                        "type": "string"
                    },
                    "value": {
                        "enum": [
                            0,
                            1
                        ],
                        "options": [
                            {
                                "label": "ENUM_0_MESSAGE",
                                "value": 0
                            },
                            {
                                "label": "ENUM_1_ALARM",
                                "value": 1
                            }
                        ],
                        "type": "integer"
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!=",
                            "<",
                            ">",
                            "<=",
                            ">="
                        ],
                        "type": "string"
                    },
                    "path": {
                        "enum": [
                            "severity"
                        ],
                        "type": "string"
                    },
                    "value": {
                        "$ref": "tchmi:server#/definitions/severity"
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!=",
                            "<",
                            ">",
                            "<=",
                            ">="
                        ],
                        "type": "string"
                    },
                    "path": {
                        "enum": [
                            "alarmState"
                        ],
                        "type": "string"
                    },
                    "value": {
                        "$ref": "tchmi:server#/definitions/alarmState"
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!=",
                            "<",
                            ">",
                            "<=",
                            ">="
                        ],
                        "type": "string"
                    },
                    "path": {
                        "enum": [
                            "confirmationState"
                        ],
                        "type": "string"
                    },
                    "value": {
                        "$ref": "tchmi:server#/definitions/confirmationState"
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
                "properties": {
                    "comparator": {
                        "enum": [
                            "==",
                            "!="
                        ],
                        "type": "string"
                    },
                    "path": {
                        "enum": [
                            "isActive"
                        ],
                        "type": "string"
                    },
                    "value": {
                        "type": "boolean"
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
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
                        "pattern": "^payload::",
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
                            }
                        ]
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
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
                        "pattern": "^params::",
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
                            }
                        ]
                    }
                },
                "required": [
                    "path",
                    "comparator",
                    "value"
                ],
                "type": "object"
            },
            {
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
                "$ref": "tchmi:server#/definitions/eventFilter"
            }
        ]
    },
    "type": "array"
}
```
