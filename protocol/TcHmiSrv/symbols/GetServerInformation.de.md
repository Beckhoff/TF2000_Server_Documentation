# Get information about the server.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"GetServerInformation"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get information about the server.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetServerInformation"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get information about the server.
```javascript
TcHmi.Server.readSymbol('GetServerInformation', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'GetServerInformation=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "type": "object"
    }
}
```
