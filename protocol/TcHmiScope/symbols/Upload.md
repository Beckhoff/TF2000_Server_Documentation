# Get Data for a specific ScopeChart.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.Upload"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| fileName | string | Name for uploaded .svdx file. |
| data | string | Data as base64. |
| chunkType | number | Chunktype: 0=file is sent as a whole, 1=beginning of a file, 2=middle part of a file (any number of times), 3=end of a file |
| fileSize | number | Complete size of .svdx file |
| persist | boolean | Whether a file should be persisted (after shutdown of the extension the file will be deleted). |

## Sample request - WebSocket

Get Data for ScopeChart named 'MyScopeYT Chart'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.Upload",
            "writeValue": {
                "chunkType": 1,
                "data": "SEVMTE8=",
                "fileName": "Test.svdx",
                "fileSize": 142799,
                "persist": true
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get Data for ScopeChart named 'MyScopeYT Chart'.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.Upload',
    {
        "chunkType": 1,
        "data": "SEVMTE8=",
        "fileName": "Test.svdx",
        "fileSize": 142799,
        "persist": true
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
            'TcHmiScope.Upload=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "chunkType": {
                "description": "Chunktype: 0=file is sent as a whole, 1=beginning of a file, 2=middle part of a file (any number of times), 3=end of a file",
                "enum": [
                    0,
                    1,
                    2,
                    3
                ],
                "type": "number"
            },
            "data": {
                "description": "Data as base64.",
                "type": "string"
            },
            "fileName": {
                "description": "Name for uploaded .svdx file.",
                "type": "string"
            },
            "fileSize": {
                "description": "Complete size of .svdx file",
                "type": "number"
            },
            "persist": {
                "description": "Whether a file should be persisted (after shutdown of the extension the file will be deleted).",
                "type": "boolean"
            }
        },
        "required": [
            "fileName",
            "data",
            "chunkType"
        ],
        "type": "object"
    }
}
```
