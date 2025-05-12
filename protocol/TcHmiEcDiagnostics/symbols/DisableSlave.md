# Disable a specific slave of a specific EtherCAT master.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.DisableSlave"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| device | string |
| slaveAddr | integer |

## Sample request - WebSocket

Disable the slave with the physical address 1003 of the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.DisableSlave",
            "writeValue": {
                "device": "Device1",
                "slaveAddr": 1003
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Disable the slave with the physical address 1003 of the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.DisableSlave',
    {
        "device": "Device1",
        "slaveAddr": 1003
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
            'TcHmiEcDiagnostics.DisableSlave=' +
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
            }
        },
        "required": [
            "device",
            "slaveAddr"
        ],
        "type": "object"
    }
}
```
