# Get information about the slaves of a specific EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.GetSlaves"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get information about the slaves of the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.GetSlaves",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get information about the slaves of the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.GetSlaves',
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
            'TcHmiEcDiagnostics.GetSlaves=' +
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
            "disabledSlaves": {
                "items": {
                    "$ref": "#/definitions/slave"
                },
                "type": "array"
            },
            "hotConnectGroups": {
                "items": {
                    "$ref": "#/definitions/slave"
                },
                "type": "array"
            },
            "master": {
                "properties": {
                    "configuredSlave": {
                        "$ref": "#/definitions/slave"
                    },
                    "portPhysic": {
                        "type": "integer"
                    }
                },
                "type": "object"
            },
            "slavesCount": {
                "type": "number"
            }
        },
        "required": [
            "config",
            "slavesCount"
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
