# List of physical addresses of all slaves with forced process data.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.ListSlavesWithForcedProcessData"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

List physical addresses of all slaves with forced process data of the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.ListSlavesWithForcedProcessData",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

List physical addresses of all slaves with forced process data of the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.ListSlavesWithForcedProcessData',
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
            'TcHmiEcDiagnostics.ListSlavesWithForcedProcessData=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "config": {
            "properties": {
                "masterNetId": {
                    "type": "string"
                },
                "targetNetId": {
                    "type": "string"
                }
            },
            "type": "object"
        },
        "function": true,
        "slaves": {
            "items": {
                "type": "integer"
            },
            "type": "array"
        }
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
