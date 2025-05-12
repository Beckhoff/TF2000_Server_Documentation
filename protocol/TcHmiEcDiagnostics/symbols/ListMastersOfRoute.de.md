# Get a list of the EtherCAT masters that are available via a specific ADS route.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.ListMastersOfRoute"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

List the EtherCAT masters of the '127.0.0.1.1.1' route.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.ListMastersOfRoute",
            "writeValue": "127.0.0.1.1.1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

List the EtherCAT masters of the '127.0.0.1.1.1' route.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.ListMastersOfRoute',
    "127.0.0.1.1.1",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiEcDiagnostics.ListMastersOfRoute=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "items": [
            {
                "properties": {
                    "label": {
                        "type": "string"
                    },
                    "value": {
                        "format": "amsnetid",
                        "type": "string"
                    }
                },
                "required": [
                    "label",
                    "value"
                ],
                "type": "object"
            }
        ],
        "type": "array"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
