# Release a specific value in the process data of a specific EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.ReleaseProcessDataValues"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Release a specific value in the process data of the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.ReleaseProcessDataValues",
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

Release a specific value in the process data of the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.ReleaseProcessDataValues',
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
            'TcHmiEcDiagnostics.ReleaseProcessDataValues=' +
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
        "oneOf": [
            {
                "type": "string"
            },
            {
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
                                "$ref": "#/definitions/EcDiagnosticsProcessDataObjectEntryID"
                            }
                        ],
                        "type": "array"
                    }
                },
                "type": "object"
            }
        ]
    }
}
```
