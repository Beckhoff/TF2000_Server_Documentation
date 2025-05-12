# Get symbol access with the current user.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"GetSymbolAccess"` |
| Kategorie | usersAndSessions |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

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

## Beispiel-Anfrage - JavaScript

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

## JSON-Schema

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
