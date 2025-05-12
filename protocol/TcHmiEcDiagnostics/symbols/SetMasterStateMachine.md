# Set the state machine of a specific EtherCAT master.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.SetMasterStateMachine"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| device | string |
| state | integer |

## Sample request - WebSocket

Set the state machine of the 'Device1' EtherCAT master to operational.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.SetMasterStateMachine",
            "writeValue": {
                "device": "Device1",
                "state": 8
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Set the state machine of the 'Device1' EtherCAT master to operational.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.SetMasterStateMachine',
    {
        "device": "Device1",
        "state": 8
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiEcDiagnostics.SetMasterStateMachine=' +
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
        "properties": {
            "device": {
                "type": "string"
            },
            "state": {
                "type": "integer"
            }
        },
        "required": [
            "device",
            "state"
        ],
        "type": "object"
    }
}
```
