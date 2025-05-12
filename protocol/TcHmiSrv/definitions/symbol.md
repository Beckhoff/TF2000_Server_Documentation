# Symbol

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
    "configDescription": "DESC_SYMBOL",
    "properties": {
        "ACCESS": {
            "allOf": [
                {
                    "$ref": "tchmi:server#/definitions/accessEnum"
                },
                {
                    "configDescription": "DESC_ACCESS"
                }
            ]
        },
        "CUSTOMERDATA": {
            "type": "string",
            "visibility": "HideInEngineering"
        },
        "DOMAIN": {
            "description": "Domain of the symbol",
            "optionMethod": {
                "symbol": "ListDomains"
            },
            "type": "string"
        },
        "DYNAMIC": {
            "default": true,
            "description": "Only dynamic symbols can be removed.",
            "type": "boolean",
            "visibility": "HideInEngineering"
        },
        "EXTENSION_DATA_DOMAINS": {
            "configDescription": "DESC_EXTENSION_DATA_DOMAINS",
            "items": {
                "optionMethod": {
                    "symbol": "ListDomains"
                },
                "type": "string"
            },
            "type": "array",
            "uniqueItems": true
        },
        "HIDDEN": {
            "default": false,
            "description": "Only display this symbol in the advanced view.",
            "type": "boolean",
            "visibility": "HideInEngineering"
        },
        "MAPPING": {
            "description": "This is how the given domain will access the symbol.",
            "type": "string"
        },
        "OPTIONS": {
            "additionalProperties": {},
            "type": "object",
            "visibility": "HideInEngineering"
        },
        "REAUTHENTICATION_REQUIRED": {
            "default": false,
            "description": "Command for writing this symbol requires a login command.",
            "type": "boolean"
        },
        "SCHEMA": {
            "allOf": [
                {
                    "$ref": "tchmi:server#/definitions/schemaRef"
                },
                {
                    "description": "Json schema describing the output parameters of the symbol."
                }
            ]
        },
        "SUBSYMBOL_MAPPING": {
            "description": "This sub-path is not forwarded to the extension. The server automatically browses into the result of the mapped symbol.",
            "type": "string"
        },
        "USEMAPPING": {
            "default": true,
            "description": "If true the mapping will be used, otherwise the symbol will be evaluated in the server.",
            "type": "boolean"
        }
    },
    "required": [
        "DOMAIN",
        "MAPPING",
        "ACCESS"
    ],
    "type": "object"
}
```
