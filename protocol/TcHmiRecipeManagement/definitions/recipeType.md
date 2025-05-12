# Recipe type is a general description of a set of symbols

## General information

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "additionalProperties": false,
    "configDescription": "DESC_RECIPETYPE",
    "properties": {
        "members": {
            "additionalProperties": {
                "anyOf": [
                    {
                        "properties": {
                            "comment": {
                                "default": "",
                                "type": "string"
                            },
                            "defaultValue": {},
                            "enabled": {
                                "default": false,
                                "type": "boolean"
                            },
                            "group": {
                                "default": "",
                                "type": "string"
                            },
                            "order": {
                                "type": "integer"
                            },
                            "schema": {
                                "$ref": "tchmi:server#/definitions/schemaRef"
                            },
                            "symbol": {
                                "default": "",
                                "type": "string"
                            },
                            "unit": {
                                "default": "",
                                "type": "string"
                            },
                            "version": {
                                "default": 1.0,
                                "type": "number"
                            }
                        },
                        "required": [
                            "symbol",
                            "defaultValue"
                        ],
                        "type": "object"
                    },
                    {
                        "properties": {
                            "comment": {
                                "default": "",
                                "type": "string"
                            },
                            "enabled": {
                                "default": true,
                                "type": "boolean"
                            },
                            "group": {
                                "default": "",
                                "type": "string"
                            },
                            "order": {
                                "type": "integer"
                            },
                            "recipeType": {
                                "type": "string"
                            },
                            "unit": {
                                "default": "",
                                "type": "string"
                            }
                        },
                        "required": [
                            "recipeType"
                        ],
                        "type": "object"
                    }
                ]
            },
            "type": "object"
        },
        "options": {
            "additionalProperties": {},
            "properties": {
                "comment": {
                    "default": "",
                    "type": "string"
                },
                "enabled": {
                    "enum": [
                        "None",
                        "Disabled"
                    ],
                    "type": "string"
                }
            },
            "type": "object"
        },
        "recipeTypeNames": {
            "items": {
                "type": "string"
            },
            "uniqueItems": true
        }
    },
    "required": [
        "members"
    ],
    "type": "object"
}
```
