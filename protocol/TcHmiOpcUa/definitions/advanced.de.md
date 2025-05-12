# Erweiterte Einstellungen

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |

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
        "arrayCloseReplacement": {
            "description": "descArrayCloseReplacement",
            "type": "string"
        },
        "arrayOpenReplacement": {
            "description": "descArrayOpenReplacement",
            "type": "string"
        },
        "asteriskReplacement": {
            "description": "descAsteriskReplacement",
            "type": "string"
        },
        "browseValueSubelements": {
            "description": "descBrowseValueSubelements",
            "type": "boolean"
        },
        "colonReplacement": {
            "description": "descColonReplacement",
            "type": "string"
        },
        "definitionNameMode": {
            "default": 0,
            "description": "descDefinitionNameMode",
            "enum": [
                0,
                1,
                2
            ],
            "options": [
                {
                    "label": "useReferenceTypesAsDefinitionNames",
                    "value": 0
                },
                {
                    "label": "useNodeTypesAsDefinitionNames",
                    "value": 1
                },
                {
                    "label": "useNodeIdsAsDefinitionNames",
                    "value": 2
                }
            ],
            "type": "integer"
        },
        "doubleColonReplacement": {
            "description": "descDoubleColonReplacement",
            "type": "string"
        },
        "forbiddenReferenceNodes": {
            "description": "descForbiddenReferenceNodes",
            "properties": {
                "binaryNodes": {
                    "items": {
                        "format": "base64",
                        "type": "string"
                    },
                    "type": "array"
                },
                "guidNodes": {
                    "items": {
                        "type": "string"
                    },
                    "type": "array"
                },
                "integerNodes": {
                    "items": {
                        "type": "number"
                    },
                    "type": "array"
                },
                "stringNodes": {
                    "items": {
                        "type": "string"
                    },
                    "type": "array"
                }
            },
            "type": "object"
        },
        "ignoreNodes": {
            "description": "descIgnoreNodes",
            "properties": {
                "binaryNodes": {
                    "items": {
                        "format": "base64",
                        "type": "string"
                    },
                    "type": "array"
                },
                "guidNodes": {
                    "items": {
                        "type": "string"
                    },
                    "type": "array"
                },
                "integerNodes": {
                    "items": {
                        "type": "number"
                    },
                    "type": "array"
                },
                "stringNodes": {
                    "items": {
                        "type": "string"
                    },
                    "type": "array"
                }
            },
            "type": "object"
        },
        "percentReplacement": {
            "description": "descPercentReplacement",
            "type": "string"
        },
        "startPoint": {
            "default": {
                "binaryIdentifier": "",
                "guidIdentifier": "",
                "identifierType": 0,
                "integerIdentifier": 85,
                "namespaceIndex": 0,
                "stringIdentifier": ""
            },
            "description": "descStartPoint",
            "properties": {
                "binaryIdentifier": {
                    "format": "base64",
                    "type": "string"
                },
                "guidIdentifier": {
                    "type": "string"
                },
                "identifierType": {
                    "default": 0,
                    "enum": [
                        0,
                        1,
                        2,
                        3
                    ],
                    "options": [
                        {
                            "label": "Numeric",
                            "value": 0
                        },
                        {
                            "label": "String",
                            "value": 1
                        },
                        {
                            "label": "GUID",
                            "value": 2
                        },
                        {
                            "label": "Binary",
                            "value": 3
                        }
                    ],
                    "type": "integer"
                },
                "integerIdentifier": {
                    "type": "number"
                },
                "namespaceIndex": {
                    "type": "number"
                },
                "stringIdentifier": {
                    "type": "string"
                }
            },
            "type": "object"
        },
        "verticalLineReplacement": {
            "description": "descVerticalLineReplacement",
            "type": "string"
        }
    },
    "required": [
        "arrayCloseReplacement",
        "arrayOpenReplacement",
        "browseValueSubelements",
        "doubleColonReplacement",
        "colonReplacement",
        "verticalLineReplacement",
        "asteriskReplacement",
        "percentReplacement",
        "definitionNameMode",
        "ignoreNodes",
        "forbiddenReferenceNodes",
        "startPoint"
    ],
    "type": "object"
}
```
