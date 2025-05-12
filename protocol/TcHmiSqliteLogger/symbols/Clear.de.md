# Remove all persistent events from the database.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteLogger.Clear"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Remove all persistent verbose, info and warning events from the database.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSqliteLogger.Clear",
            "writeValue": {
                "match": [
                    {
                        "comparator": "<=",
                        "path": "severity",
                        "value": 2
                    }
                ]
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Remove all persistent verbose, info and warning events from the database.
```javascript
TcHmi.Server.writeSymbol('TcHmiSqliteLogger.Clear',
    {
        "match": [
            {
                "comparator": "<=",
                "path": "severity",
                "value": 2
            }
        ]
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
            'TcHmiSqliteLogger.Clear=' +
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
        "anyOf": [
            {
                "properties": {
                    "match": {
                        "$ref": "tchmi:server#/definitions/eventFilter"
                    }
                },
                "required": [
                    "match"
                ],
                "type": "object"
            },
            {
                "$ref": "tchmi:general#/definitions/VOID"
            }
        ]
    }
}
```
