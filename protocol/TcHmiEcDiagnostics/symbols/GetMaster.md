# Get information about a specific EtherCAT master.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.GetMaster"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Get information about the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.GetMaster",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get information about the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.GetMaster',
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
            'TcHmiEcDiagnostics.GetMaster=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "config": {
                "properties": {
                    "targetNetId": {
                        "type": "string"
                    }
                },
                "type": "object"
            },
            "name": {
                "type": "string"
            },
            "netId": {
                "type": "string"
            }
        },
        "required": [
            "config",
            "name",
            "netId"
        ],
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
