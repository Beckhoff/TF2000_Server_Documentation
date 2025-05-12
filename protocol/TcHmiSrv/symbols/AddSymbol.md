# Create a new mapped symbol.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"AddSymbol"` |
| Category | symbols |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| NAME | string | Name of the symbol |
| AUTOMAP | boolean | Automatically obtain symbol information such as options and schema from the domain. |
| DOMAIN | string |  |
| USEMAPPING | boolean |  |
| CUSTOMERDATA | string |  |
| OPTIONS | object |  |
| MAPPING | string |  |
| SUBSYMBOL_MAPPING | string |  |
| ACCESS |  |  |
| HIDDEN | boolean |  |
| SCHEMA | schemaRef |  |
| USERGROUPS |  |  |
| CHECKCOMPLEXITY | boolean | Do not add symbol, check complexity of added symbol instead |

## Sample request - WebSocket

Create a new mapped symbol for a specific PLC variable.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "AddSymbol",
            "writeValue": {
                "ACCESS": 3,
                "AUTOMAP": true,
                "DOMAIN": "ADS",
                "MAPPING": "PLC1::MAIN::nCounter",
                "NAME": "PLC1.MAIN.nCounter"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Create a new mapped symbol for a specific PLC variable.
```javascript
TcHmi.Server.writeSymbol('AddSymbol',
    {
        "ACCESS": 3,
        "AUTOMAP": true,
        "DOMAIN": "ADS",
        "MAPPING": "PLC1::MAIN::nCounter",
        "NAME": "PLC1.MAIN.nCounter"
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'AddSymbol=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "symbols",
    "readValue": {
        "function": true,
        "properties": {
            "name": {
                "type": "string"
            },
            "symbolCount": {
                "type": "integer"
            },
            "validSymbolCount": {
                "type": "boolean"
            }
        },
        "required": [
            "name"
        ],
        "type": "object"
    },
    "writeValue": {
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
            "AUTOMAP": {
                "default": false,
                "description": "Automatically obtain symbol information such as options and schema from the domain.",
                "type": "boolean"
            },
            "CHECKCOMPLEXITY": {
                "default": false,
                "description": "Do not add symbol, check complexity of added symbol instead",
                "type": "boolean"
            },
            "CUSTOMERDATA": {
                "type": "string"
            },
            "DOMAIN": {
                "type": "string"
            },
            "HIDDEN": {
                "default": false,
                "type": "boolean"
            },
            "MAPPING": {
                "type": "string"
            },
            "NAME": {
                "description": "Name of the symbol",
                "type": "string"
            },
            "OPTIONS": {
                "additionalProperties": {},
                "type": "object"
            },
            "SCHEMA": {
                "$ref": "tchmi:server#/definitions/schemaRef"
            },
            "SUBSYMBOL_MAPPING": {
                "type": "string"
            },
            "USEMAPPING": {
                "default": true,
                "type": "boolean"
            },
            "USERGROUPS": {
                "anyOf": [
                    {
                        "items": {
                            "type": "string"
                        },
                        "type": "array"
                    },
                    {
                        "additionalProperties": {
                            "$ref": "tchmi:server#/definitions/accessEnum"
                        },
                        "type": "object"
                    }
                ]
            }
        },
        "required": [
            "DOMAIN",
            "MAPPING"
        ],
        "type": "object"
    }
}
```
