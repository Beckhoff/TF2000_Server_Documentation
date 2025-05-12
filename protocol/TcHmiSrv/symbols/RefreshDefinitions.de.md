# Refresh all definitions of a particular type.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"RefreshDefinitions"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Refresh the 'project' definitions.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "RefreshDefinitions",
            "writeValue": "project"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Refresh the 'project' definitions.
```javascript
TcHmi.Server.writeSymbol('RefreshDefinitions',
    "project",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'RefreshDefinitions=' +
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
        "enum": [
            "framework",
            "project",
            "general"
        ],
        "type": "string"
    }
}
```
