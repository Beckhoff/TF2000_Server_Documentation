# Get a list of all enabled target systems.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiEventLogger.ListEnabledTargetSystems"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEventLogger.ListEnabledTargetSystems"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEventLogger.ListEnabledTargetSystems', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEventLogger.ListEnabledTargetSystems=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "items": {
            "type": "string"
        },
        "type": "array"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
