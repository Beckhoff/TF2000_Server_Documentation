# Upload file to server.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"Upload"` |
| Category | configurationsAndFilesystem |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| isDirectory | boolean |  |
| fileName | string | Name of the file. |
| data | string | Data of the file. |
| checkSum | string | Checksum of the file as MD5 hexadecimal-string. |
| chunkType | integer |  |
| domain | string | Upload extension dll to remote filesystem. |

## Sample request - WebSocket

Upload file `test.txt` with data `Hello World` to the current DocRoot.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Upload",
            "writeValue": {
                "data": "SGVsbG8gV29ybGQ=",
                "fileName": "/test.txt"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Upload file `test.txt` with data `Hello World` to the current DocRoot.
```javascript
TcHmi.Server.writeSymbol('Upload',
    {
        "data": "SGVsbG8gV29ybGQ=",
        "fileName": "/test.txt"
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
            'Upload=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "configurationsAndFilesystem",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "additionalProperties": false,
        "properties": {
            "checkSum": {
                "description": "Checksum of the file as MD5 hexadecimal-string.",
                "type": "string"
            },
            "chunkType": {
                "default": 0,
                "enum": [
                    0,
                    1,
                    2,
                    3
                ],
                "type": "integer"
            },
            "data": {
                "description": "Data of the file.",
                "format": "base64",
                "type": "string"
            },
            "domain": {
                "description": "Upload extension dll to remote filesystem.",
                "type": "string"
            },
            "fileName": {
                "description": "Name of the file.",
                "type": "string"
            },
            "isDirectory": {
                "default": false,
                "type": "boolean"
            }
        },
        "required": [
            "fileName"
        ],
        "type": "object"
    }
}
```
