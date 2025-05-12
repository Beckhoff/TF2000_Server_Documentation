# Set the state machine of the slave of a specific EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.SetSlaveStateMachine"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| device | string |
| slaveAddr | integer |
| state | integer |

## Beispiel-Anfrage - WebSocket

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

## Beispiel-Anfrage - JavaScript

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

## JSON-Schema

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
