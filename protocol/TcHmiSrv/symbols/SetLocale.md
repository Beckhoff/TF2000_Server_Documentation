# Change the locale of the current session.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"SetLocale"` |
| Category | usersAndSessions |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Set current locale to `en`
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "SetLocale",
            "writeValue": "en"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Set current locale to `en`
```javascript
TcHmi.Server.writeSymbol('SetLocale',
    "en",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'SetLocale=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "format": "locale",
        "type": "string"
    }
}
```
