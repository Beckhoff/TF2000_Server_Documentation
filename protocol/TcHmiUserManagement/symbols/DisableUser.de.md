# Disable a user.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.DisableUser"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Disable user `test`.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.DisableUser",
            "writeValue": "test"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Disable user `test`.
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.DisableUser',
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
            'TcHmiUserManagement.DisableUser=' +
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
