# Get information of specific file.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"GetFileInformation"` |
| Kategorie | configurationsAndFilesystem |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get file information of '/test.txt'
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetFileInformation",
            "writeValue": "/test.txt"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get file information of '/test.txt'
```javascript
TcHmi.Server.writeSymbol('GetFileInformation',
    "/test.txt",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'GetFileInformation=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "configurationsAndFilesystem",
    "readValue": {
        "allOf": [
            {
                "function": true
            },
            {
                "$ref": "tchmi:server#/definitions/fileInfo"
            },
            {
                "required": [
                    "modificationTime",
                    "fileSize",
                    "access"
                ]
            }
        ]
    },
    "writeValue": {
        "type": "string"
    }
}
```
