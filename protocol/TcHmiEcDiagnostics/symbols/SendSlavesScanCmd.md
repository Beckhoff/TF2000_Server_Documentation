# Scan the network for slaves of an EtherCAT master.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.SendSlavesScanCmd"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

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

## Sample request - JavaScript

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

## JSON schema

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
