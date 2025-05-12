# Delete all scope records from scope server or only those records which you could attached to and which you started yourself (from all scope servers).

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.DeleteScopeServerRecords"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| amsNetId | string |
| deleteAllScopeRecords | boolean |

## Beispiel-Anfrage - WebSocket

Delete all scope records from scope server or only those records which you could attached to and which you started yourself (from all scope servers).
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.DeleteScopeServerRecords",
            "writeValue": {
                "amsNetId": "172.17.62.63.1.1",
                "deleteAllScopeRecords": true
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Delete all scope records from scope server or only those records which you could attached to and which you started yourself (from all scope servers).
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.DeleteScopeServerRecords',
    {
        "amsNetId": "172.17.62.63.1.1",
        "deleteAllScopeRecords": true
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
            'TcHmiScope.DeleteScopeServerRecords=' +
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
            "amsNetId": {
                "type": "string"
            },
            "deleteAllScopeRecords": {
                "type": "boolean"
            }
        },
        "required": [
            "amsNetId",
            "deleteAllScopeRecords"
        ],
        "type": "object"
    }
}
```
