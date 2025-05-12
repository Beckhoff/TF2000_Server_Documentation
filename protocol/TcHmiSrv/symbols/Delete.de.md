# Delete the given file from the containing virtual directory. If domain is set try to delete the extension file.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"Delete"` |
| Kategorie | configurationsAndFilesystem |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| fileName | string | Name of the file to delete. |
| domain | string | Delete file form extension. |

## Beispiel-Anfrage - WebSocket

Delete file `test.txt` from the current DocRoot.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Delete",
            "writeValue": {
                "fileName": "/test.txt"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Delete file `test.txt` from the current DocRoot.
```javascript
TcHmi.Server.writeSymbol('Delete',
    {
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
            'Delete=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "configurationsAndFilesystem",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "properties": {
            "domain": {
                "description": "Delete file form extension.",
                "type": "string"
            },
            "fileName": {
                "description": "Name of the file to delete.",
                "type": "string"
            }
        },
        "required": [
            "fileName"
        ],
        "type": "object"
    }
}
```
