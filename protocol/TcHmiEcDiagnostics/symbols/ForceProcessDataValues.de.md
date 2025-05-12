# Force a specific value in the process data of a specific EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.ForceProcessDataValues"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| device | string |
| slaveAddr | integer |
| values | array |

## Beispiel-Anfrage - WebSocket

Force a specific value in the process data of the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.ForceProcessDataValues",
            "writeValue": {
                "device": "Device1",
                "slaveAddr": 1003,
                "values": [
                    {
                        "entryIndex": "#x6000",
                        "entrySubIndex": "1",
                        "entryValue": true,
                        "io": "input",
                        "objectIndex": "#x1a00"
                    }
                ]
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Force a specific value in the process data of the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.ForceProcessDataValues',
    {
        "device": "Device1",
        "slaveAddr": 1003,
        "values": [
            {
                "entryIndex": "#x6000",
                "entrySubIndex": "1",
                "entryValue": true,
                "io": "input",
                "objectIndex": "#x1a00"
            }
        ]
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
            'TcHmiEcDiagnostics.ForceProcessDataValues=' +
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
            "values": {
                "items": [
                    {
                        "allOf": [
                            {
                                "$ref": "#/definitions/EcDiagnosticsProcessDataObjectEntryID"
                            },
                            {
                                "$ref": "#/definitions/EcDiagnosticsProcessDataObjectEntryValue"
                            }
                        ]
                    }
                ],
                "type": "array"
            }
        },
        "type": "object"
    }
}
```
