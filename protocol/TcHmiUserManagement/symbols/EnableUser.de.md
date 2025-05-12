# Enable a user.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.EnableUser"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Enable user `test`.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.EnableUser",
            "writeValue": "test"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Enable user `test`.
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.EnableUser',
    "test",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiUserManagement.EnableUser=' +
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
        "description": "Name of the user.",
        "type": "string"
    }
}
```
