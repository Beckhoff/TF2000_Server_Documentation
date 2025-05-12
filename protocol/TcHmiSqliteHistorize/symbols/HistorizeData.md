# Get the historized data.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Full symbol path | `"TcHmiSqliteHistorize.HistorizeData"` |
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
            "symbol": "TcHmiSqliteHistorize.HistorizeData"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteHistorize.HistorizeData', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteHistorize.HistorizeData=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
