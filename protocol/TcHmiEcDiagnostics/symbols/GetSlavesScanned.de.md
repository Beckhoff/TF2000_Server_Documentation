# Get a list of scanned slaves in the network of an EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.GetSlavesScanned"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get a list of scanned slaves in the network of the 'Device1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.GetSlavesScanned",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get a list of scanned slaves in the network of the 'Device1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.GetSlavesScanned',
    "Device1",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiEcDiagnostics.GetSlavesScanned=' +
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
            "slaves": {
                "items": [
                    {
                        "properties": {
                            "addr": {
                                "type": "integer"
                            },
                            "productCode": {
                                "type": "integer"
                            },
                            "revisionNumber": {
                                "type": "integer"
                            },
                            "serialNumber": {
                                "type": "integer"
                            },
                            "vendorId": {
                                "type": "integer"
                            },
                            "vendorLabelName": {
                                "type": "string"
                            },
                            "vendorMemberName": {
                                "type": "string"
                            }
                        },
                        "required": [
                            "addr",
                            "productCode",
                            "revisionNumber",
                            "serialNumber",
                            "vendorId",
                            "vendorLabelName",
                            "vendorMemberName"
                        ],
                        "type": "object"
                    }
                ],
                "type": "array"
            },
            "updated": {
                "type": "string"
            }
        },
        "required": [
            "config",
            "slaves",
            "updated"
        ],
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
