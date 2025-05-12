# Remove the alarms from the event database.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiAlarm"` |
| Full symbol path | `"TcHmiAlarm.ClearLoggedEvents"` |
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
            "symbol": "TcHmiAlarm.ClearLoggedEvents"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiAlarm.ClearLoggedEvents', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiAlarm.ClearLoggedEvents=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true
    }
}
```
