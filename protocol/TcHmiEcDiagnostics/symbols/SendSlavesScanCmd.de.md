# Scan the network for slaves of an EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.SendSlavesScanCmd"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Scan the network for slaves of the 'Device1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.SendSlavesScanCmd",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Scan the network for slaves of the 'Device1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.SendSlavesScanCmd',
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
            'TcHmiEcDiagnostics.SendSlavesScanCmd=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "access": 2,
    "readValue": {
        "function": true
    },
    "writeValue": {
        "type": "string"
    }
}
```
