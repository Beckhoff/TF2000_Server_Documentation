# Get information about the connections between the HMI server and the configured EtherCAT masters.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.Diagnostics"` |
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
            "symbol": "TcHmiEcDiagnostics.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEcDiagnostics.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEcDiagnostics.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "devices": {
                "additionalProperties": {
                    "properties": {
                        "connectionState": {
                            "propertyOrder": 4,
                            "type": "string"
                        },
                        "enabled": {
                            "propertyOrder": 1,
                            "type": "boolean",
                            "visibility": "HideInEngineering"
                        },
                        "master": {
                            "propertyOrder": 7,
                            "type": "string"
                        },
                        "masterState": {
                            "propertyOrder": 8,
                            "type": "string"
                        },
                        "target": {
                            "propertyOrder": 2,
                            "type": "string"
                        },
                        "targetAdsState": {
                            "propertyOrder": 6,
                            "type": "string"
                        },
                        "targetAdsVersion": {
                            "propertyOrder": 5,
                            "type": "string"
                        },
                        "targetAvailable": {
                            "propertyOrder": 3,
                            "type": "boolean",
                            "visibility": "HideInEngineering"
                        }
                    },
                    "required": [
                        "enabled",
                        "target",
                        "targetAvailable",
                        "connectionState",
                        "master"
                    ],
                    "type": "object"
                },
                "type": "object"
            }
        },
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
