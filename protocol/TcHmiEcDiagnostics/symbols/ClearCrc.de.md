# Clear the CRC error statistics of the EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.ClearCrc"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Clear the CRC error statistics of the EtherCAT master 'Device1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.ClearCrc",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Clear the CRC error statistics of the EtherCAT master 'Device1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.ClearCrc',
    "Device1",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiEcDiagnostics.ClearCrc=' +
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
        "type": "string"
    }
}
```
