# Ein Rezepttyp ist eine allgemeine Beschreibung eines Satzes von Symbolen

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiRecipeManagement"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

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
