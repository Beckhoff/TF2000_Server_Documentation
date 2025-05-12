# Remove all localizations from the database.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteLogger.ClearLocalizations"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Remove all localizations of all verbose, info and warning events from the database.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSqliteLogger.ClearLocalizations",
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

Remove all localizations of all verbose, info and warning events from the database.
```javascript
TcHmi.Server.writeSymbol('TcHmiSqliteLogger.ClearLocalizations',
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
            'TcHmiSqliteLogger.ClearLocalizations=' +
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
