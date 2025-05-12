# Clear the CRC error statistics of the EtherCAT master.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.ClearCrc"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

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

## Sample request - JavaScript

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

## JSON schema

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
