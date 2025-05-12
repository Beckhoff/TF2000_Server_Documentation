# Get information about the historized data that is stored in the database.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Full symbol path | `"TcHmiSqliteHistorize.Diagnostics"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSqliteHistorize.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteHistorize.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteHistorize.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "additionalProperties": false,
        "function": true,
        "properties": {
            "databaseSize": {
                "propertyOrder": 1,
                "type": "number",
                "unit": "byte"
            },
            "estimatedDatabaseSize": {
                "propertyOrder": 5,
                "type": "number",
                "unit": "byte"
            },
            "estimatedDatabaseSizePerSymbol": {
                "additionalProperties": {
                    "type": "number",
                    "unit": "byte"
                },
                "type": "object"
            },
            "numEntries": {
                "configDescription": "descNumEntries",
                "propertyOrder": 2,
                "type": "integer"
            },
            "numEntriesLifetime": {
                "configDescription": "descNumEntries",
                "propertyOrder": 3,
                "type": "number"
            },
            "recordingTime": {
                "format": "timespan",
                "propertyOrder": 4,
                "type": "string"
            }
        },
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
