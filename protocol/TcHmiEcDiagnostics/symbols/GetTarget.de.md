# Get information about a specific EtherCAT target.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.GetTarget"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get information about the 'Device1' EtherCAT target.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.GetTarget",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get information about the 'Device1' EtherCAT target.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.GetTarget',
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
            'TcHmiEcDiagnostics.GetTarget=' +
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
            "available": {
                "type": "boolean"
            },
            "config": {
                "properties": {
                    "masterNetId": {
                        "format": "amsnetid",
                        "type": "string"
                    }
                },
                "required": [
                    "masterNetId"
                ],
                "type": "object"
            },
            "name": {
                "type": "string"
            },
            "netId": {
                "type": "string"
            },
            "sysServiceAdsState": {
                "type": "integer"
            }
        },
        "required": [
            "available",
            "config",
            "name",
            "netId",
            "sysServiceAdsState"
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
