# Get the schema of a specific mapped symbol.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"GetSchema"` |
| Visibility | AlwaysShow |

## Version 1.0

Only the schema of the first version is returned.
## Version 2.0

Since version 2.0, the 'mergeSettings' parameter is supported and active by default and the 'AllVersions' resolve type can be used to get the schema of the different versions.
## Sample request - WebSocket

Get read schema for symbol test1.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetSchema",
            "writeValue": {
                "symbol": "test1"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get read schema for symbol test1.
```javascript
TcHmi.Server.writeSymbol('GetSchema',
    {
        "symbol": "test1"
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
            'GetSchema=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "symbols",
    "readValue": {
        "anyOf": [
            {
                "function": true,
                "versions": [
                    1.0
                ],
                "writeValue": {
                    "properties": {
                        "resolve": {
                            "default": "None",
                            "enum": [
                                "AddRefs",
                                "Simplify",
                                "AddAllRefs",
                                "None"
                            ],
                            "type": "string"
                        },
                        "symbol": {
                            "description": "Name of the symbol.",
                            "type": "string"
                        },
                        "type": {
                            "default": "Read",
                            "enum": [
                                "Read",
                                "Write"
                            ],
                            "type": "string"
                        }
                    },
                    "required": [
                        "symbol"
                    ],
                    "type": "object"
                }
            },
            {
                "function": true,
                "versions": [
                    2.0
                ],
                "writeValue": {
                    "properties": {
                        "mergeSettings": {
                            "default": true,
                            "description": "Merge settings from the symbol configuration into the schema.",
                            "type": "boolean"
                        },
                        "resolve": {
                            "default": "None",
                            "enum": [
                                "AddRefs",
                                "Simplify",
                                "AddAllRefs",
                                "AllVersions",
                                "None"
                            ],
                            "type": "string"
                        },
                        "symbol": {
                            "description": "Name of the symbol.",
                            "type": "string"
                        },
                        "type": {
                            "default": "Read",
                            "enum": [
                                "Read",
                                "Write"
                            ],
                            "type": "string"
                        }
                    },
                    "required": [
                        "symbol"
                    ],
                    "type": "object"
                }
            }
        ]
    },
    "versions": {
        "1.0": {
            "description": "Only the schema of the first version is returned."
        },
        "2.0": {
            "description": "Since version 2.0, the 'mergeSettings' parameter is supported and active by default and the 'AllVersions' resolve type can be used to get the schema of the different versions."
        }
    }
}
```
