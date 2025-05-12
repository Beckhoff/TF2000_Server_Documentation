# Get PLC structure of specified runtime.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSystemEngineering"` |
| Vollständiger Symbol-Pfad | `"TcHmiSystemEngineering.GetTreeView"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get PLC structure of runtime 'Runtime1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSystemEngineering.GetTreeView",
            "writeValue": "Runtime1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get PLC structure of runtime 'Runtime1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiSystemEngineering.GetTreeView',
    "Runtime1",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiSystemEngineering.GetTreeView=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "properties": {},
        "readOnly": true,
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
