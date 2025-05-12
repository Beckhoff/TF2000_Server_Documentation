# Get the schema of a specific dynamic symbol.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiMdp"` |
| Full symbol path | `"TcHmiMdp.GetSchema"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Get the JSON schema of a specific variable of the 'Local' target system.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiMdp.GetSchema",
            "writeValue": "Local::CPU[0]::CurrentCpuTemperature"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get the JSON schema of a specific variable of the 'Local' target system.
```javascript
TcHmi.Server.writeSymbol('TcHmiMdp.GetSchema',
    "Local::CPU[0]::CurrentCpuTemperature",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiMdp.GetSchema=' +
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
