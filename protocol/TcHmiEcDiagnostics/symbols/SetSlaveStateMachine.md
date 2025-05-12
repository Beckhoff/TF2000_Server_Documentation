# Set the state machine of the slave of a specific EtherCAT master.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.SetSlaveStateMachine"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| device | string |
| slaveAddr | integer |
| state | integer |

## Sample request - WebSocket

Set the state machine of the slave with the physical address 1003 of the 'Device1' EtherCAT master to operational.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.SetSlaveStateMachine",
            "writeValue": {
                "device": "Device1",
                "slaveAddr": 1003,
                "state": 8
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Set the state machine of the slave with the physical address 1003 of the 'Device1' EtherCAT master to operational.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.SetSlaveStateMachine',
    {
        "device": "Device1",
        "slaveAddr": 1003,
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
            'TcHmiEcDiagnostics.SetSlaveStateMachine=' +
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
            "slaveAddr": {
                "type": "integer"
            },
            "state": {
                "type": "integer"
            }
        },
        "required": [
            "device",
            "slaveAddr",
            "state"
        ],
        "type": "object"
    }
}
```
