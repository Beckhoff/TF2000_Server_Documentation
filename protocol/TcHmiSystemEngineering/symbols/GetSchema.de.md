# Get the schema of a specific dynamic symbol.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSystemEngineering"` |
| Vollständiger Symbol-Pfad | `"TcHmiSystemEngineering.GetSchema"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get the JSON schema of a specific variable of the 'PLC1' runtime.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSystemEngineering.GetSchema",
            "writeValue": "PLC1::MAIN::nCounter"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get the JSON schema of a specific variable of the 'PLC1' runtime.
```javascript
TcHmi.Server.writeSymbol('TcHmiSystemEngineering.GetSchema',
    "PLC1::MAIN::nCounter",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiSystemEngineering.GetSchema=' +
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
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
