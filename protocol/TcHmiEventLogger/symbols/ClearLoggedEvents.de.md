# Clear the event database of a specific target system.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiEventLogger.ClearLoggedEvents"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| targetName | string |

## Beispiel-Anfrage - WebSocket

Clear the event database of a the 'Local' target system.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEventLogger.ClearLoggedEvents",
            "writeValue": {
                "targetName": "Local"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Clear the event database of a the 'Local' target system.
```javascript
TcHmi.Server.writeSymbol('TcHmiEventLogger.ClearLoggedEvents',
    {
        "targetName": "Local"
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
            'TcHmiEventLogger.ClearLoggedEvents=' +
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
    "writeValue": {
        "properties": {
            "targetName": {
                "type": "string"
            }
        },
        "required": [
            "targetName"
        ],
        "type": "object"
    }
}
```
