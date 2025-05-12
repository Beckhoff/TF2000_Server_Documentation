# Clear the frame statistics of the EtherCAT master.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.ClearFrames"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Clear the Frame statistics of the EtherCAT master 'Device1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.ClearFrames",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Clear the Frame statistics of the EtherCAT master 'Device1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.ClearFrames',
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
            'TcHmiEcDiagnostics.ClearFrames=' +
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
