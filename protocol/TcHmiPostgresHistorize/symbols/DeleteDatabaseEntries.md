# Delete records from the historized database.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Full symbol path | `"TcHmiPostgresHistorize.DeleteDatabaseEntries"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| symbolName | string |
| disableRecording | boolean |

## Sample request - WebSocket

Disable recording and delete database entries of 'MySymbol'. If 'symbolName' is not set all entries in the database will be deleted. 'disableRecording' disables the recording of one or all historize symbols depending if 'symbolName' is set.'
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiPostgresHistorize.DeleteDatabaseEntries",
            "writeValue": {
                "disableRecording": true,
                "symbolName": "MySymbol"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Disable recording and delete database entries of 'MySymbol'. If 'symbolName' is not set all entries in the database will be deleted. 'disableRecording' disables the recording of one or all historize symbols depending if 'symbolName' is set.'
```javascript
TcHmi.Server.writeSymbol('TcHmiPostgresHistorize.DeleteDatabaseEntries',
    {
        "disableRecording": true,
        "symbolName": "MySymbol"
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
            'TcHmiPostgresHistorize.DeleteDatabaseEntries=' +
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
            "disableRecording": {
                "type": "boolean"
            },
            "symbolName": {
                "type": "string"
            }
        },
        "type": "object"
    }
}
```
