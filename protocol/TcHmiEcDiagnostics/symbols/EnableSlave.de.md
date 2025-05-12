# Enable a specific slave of a specific EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.EnableSlave"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| device | string |
| slaveAddr | integer |

## Beispiel-Anfrage - WebSocket

Enable the slave with the physical address 1003 of the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.EnableSlave",
            "writeValue": {
                "device": "Device1",
                "slaveAddr": 1003
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Enable the slave with the physical address 1003 of the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.EnableSlave',
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
            'TcHmiEcDiagnostics.EnableSlave=' +
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
