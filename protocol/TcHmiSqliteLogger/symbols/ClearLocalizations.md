# Remove all localizations from the database.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Full symbol path | `"TcHmiSqliteLogger.ClearLocalizations"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

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

## Sample request - JavaScript

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

## JSON schema

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
