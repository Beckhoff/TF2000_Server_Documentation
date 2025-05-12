# Get a list of all configured EtherCAT devices.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.ListConfiguredDevices"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.ListConfiguredDevices"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEcDiagnostics.ListConfiguredDevices', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEcDiagnostics.ListConfiguredDevices=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "additionalProperties": {
            "properties": {
                "enabled": {
                    "type": "boolean"
                },
                "masterNetId": {
                    "format": "amsnetid",
                    "type": "string"
                },
                "targetNetId": {
                    "format": "amsnetid",
                    "type": "string"
                }
            },
            "required": [
                "enabled",
                "targetNetId",
                "masterNetId"
            ],
            "type": "object"
        },
        "function": true,
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
