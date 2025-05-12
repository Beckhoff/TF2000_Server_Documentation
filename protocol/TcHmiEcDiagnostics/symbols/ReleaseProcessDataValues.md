# Release a specific value in the process data of a specific EtherCAT master.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.ReleaseProcessDataValues"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

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

## Sample request - JavaScript

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

## JSON schema

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
