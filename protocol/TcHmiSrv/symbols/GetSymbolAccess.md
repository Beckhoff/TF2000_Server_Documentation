# Get symbol access with the current user.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"GetSymbolAccess"` |
| Category | usersAndSessions |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Get the symbol access for the 'Heartbeat' symbol with the current user.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetSymbolAccess",
            "writeValue": "Heartbeat"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get the symbol access for the 'Heartbeat' symbol with the current user.
```javascript
TcHmi.Server.writeSymbol('GetSymbolAccess',
    "Heartbeat",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'GetSymbolAccess=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "allOf": [
            {
                "$ref": "tchmi:server#/definitions/accessEnum"
            },
            {
                "function": true
            }
        ]
    },
    "writeValue": {
        "type": "string"
    }
}
```
