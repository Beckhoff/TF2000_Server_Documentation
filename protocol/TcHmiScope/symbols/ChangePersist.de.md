# Attach to scope record. Symbols must be called from the same socket as OpenConnection.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.ChangePersist"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| userName | string | Name of the user. |
| extensionName | string | Name of the extension. |
| fileName | string | Name of the file. |
| guid | string | Guid of the uploaded record. |
| persist | boolean | Whether a file should be persisted (after shutdown of the extension the file will be deleted). |

## Beispiel-Anfrage - WebSocket

Attach to scope record. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.ChangePersist",
            "writeValue": {
                "extensionName": "TcHmiScope",
                "fileName": "Test.svdx",
                "guid": "2997437c-6969-4fe0-8bc2-3275125f6ebd",
                "persist": true,
                "userName": "Julia"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Attach to scope record. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.ChangePersist',
    {
        "extensionName": "TcHmiScope",
        "fileName": "Test.svdx",
        "guid": "2997437c-6969-4fe0-8bc2-3275125f6ebd",
        "persist": true,
        "userName": "Julia"
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
            'TcHmiScope.ChangePersist=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

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
            "extensionName": {
                "description": "Name of the extension.",
                "type": "string"
            },
            "fileName": {
                "description": "Name of the file.",
                "type": "string"
            },
            "guid": {
                "description": "Guid of the uploaded record.",
                "type": "string"
            },
            "persist": {
                "description": "Whether a file should be persisted (after shutdown of the extension the file will be deleted).",
                "type": "boolean"
            },
            "userName": {
                "description": "Name of the user.",
                "type": "string"
            }
        },
        "required": [
            "userName",
            "extensionName",
            "fileName",
            "guid",
            "persist"
        ],
        "type": "object"
    }
}
```
