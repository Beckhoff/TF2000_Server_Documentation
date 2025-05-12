# Get a list of all files in a particular directory.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ListFiles"` |
| Sichtbarkeit | AlwaysShow |

## Version 2.0

With version 2 it is possible to return the md5 hashes of the files. In addition, all files in a directory can be returned with the "recursive" option.
## Beispiel-Anfrage - WebSocket

List the files in the root directory.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListFiles",
            "writeValue": "/"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

List the files in the root directory.
```javascript
TcHmi.Server.writeSymbol('ListFiles',
    "/",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'ListFiles=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "configurationsAndFilesystem",
    "readValue": {
        "anyOf": [
            {
                "additionalProperties": {
                    "allOf": [
                        {
                            "$ref": "tchmi:server#/definitions/fileInfo"
                        },
                        {
                            "properties": {
                                "link": {
                                    "type": "string"
                                }
                            },
                            "required": [
                                "fileFlags"
                            ]
                        }
                    ]
                },
                "function": true,
                "type": "object",
                "versions": [
                    1.0
                ],
                "writeValue": {
                    "anyOf": [
                        {
                            "type": "string"
                        },
                        {
                            "type": "null"
                        }
                    ]
                }
            },
            {
                "additionalProperties": {
                    "allOf": [
                        {
                            "$ref": "tchmi:server#/definitions/fileInfo"
                        },
                        {
                            "properties": {
                                "hash": {
                                    "description": "The md5 hash of the file",
                                    "type": "string"
                                },
                                "link": {
                                    "type": "string"
                                }
                            },
                            "required": [
                                "fileFlags"
                            ]
                        }
                    ]
                },
                "function": true,
                "type": "object",
                "versions": [
                    2.0
                ],
                "writeValue": {
                    "additionalProperties": false,
                    "properties": {
                        "hashes": {
                            "description": "If true, the hash of each file is returned.",
                            "type": "boolean"
                        },
                        "path": {
                            "description": "The path to list files from.",
                            "type": "string"
                        },
                        "recursive": {
                            "description": "If true, the entire directory tree is returned.",
                            "type": "boolean"
                        }
                    },
                    "required": [
                        "path"
                    ],
                    "type": "object",
                    "versions": [
                        2.0
                    ]
                }
            }
        ]
    },
    "versions": {
        "2.0": {
            "description": "With version 2 it is possible to return the md5 hashes of the files. In addition, all files in a directory can be returned with the \"recursive\" option."
        }
    }
}
```
