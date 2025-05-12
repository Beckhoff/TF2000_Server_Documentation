# Delete records from the historize database. If necessary enable vacuum on config page.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Full symbol path | `"TcHmiSqliteHistorize.DeleteDatabaseEntries"` |
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
            "symbol": "TcHmiSqliteHistorize.DeleteDatabaseEntries",
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
TcHmi.Server.writeSymbol('TcHmiSqliteHistorize.DeleteDatabaseEntries',
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
            'TcHmiSqliteHistorize.DeleteDatabaseEntries=' +
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
