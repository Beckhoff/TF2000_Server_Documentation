# Get the process data of a specific slave of a specific EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.GetProcessDataValues"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| device | string |
| slaveAddr | integer |
| updateForcedState | boolean |
| updateValue | boolean |

## Beispiel-Anfrage - WebSocket

Get the process data of slave with the physical address 1003 of the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.GetProcessDataValues",
            "writeValue": {
                "device": "Device1",
                "slaveAddr": 1003,
                "updateForcedState": true,
                "updateValue": true
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get the process data of slave with the physical address 1003 of the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.GetProcessDataValues',
    {
        "device": "Device1",
        "slaveAddr": 1003,
        "updateForcedState": true,
        "updateValue": true
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
            'TcHmiEcDiagnostics.GetProcessDataValues=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
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
            "in": {
                "items": [
                    {
                        "$ref": "#/definitions/EcDiagnosticsProcessDataInOutValues"
                    }
                ],
                "type": "array"
            },
            "out": {
                "items": [
                    {
                        "$ref": "#/definitions/EcDiagnosticsProcessDataInOutValues"
                    }
                ],
                "type": "array"
            }
        },
        "required": [
            "config"
        ],
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "device": {
                "type": "string"
            },
            "slaveAddr": {
                "type": "integer"
            },
            "updateForcedState": {
                "type": "boolean"
            },
            "updateValue": {
                "type": "boolean"
            }
        },
        "type": "object"
    }
}
```
