# Set the state machine of a specific EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.SetMasterStateMachine"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| device | string |
| state | integer |

## Beispiel-Anfrage - WebSocket

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

## Beispiel-Anfrage - JavaScript

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
