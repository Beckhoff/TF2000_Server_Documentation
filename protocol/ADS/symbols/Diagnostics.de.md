# Get information about the connections between the HMI server and the ADS targets.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.Diagnostics"` |
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
            "symbol": "ADS.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "runtimes": {
                "additionalProperties": {
                    "properties": {
                        "adsApplicationName": {
                            "propertyOrder": 5,
                            "type": "string",
                            "visibility": "HideInEngineering"
                        },
                        "adsProjectCompiledAt": {
                            "format": "date-time",
                            "propertyOrder": 7,
                            "type": "string",
                            "visibility": "HideInEngineering"
                        },
                        "adsProjectName": {
                            "propertyOrder": 6,
                            "type": "string"
                        },
                        "adsState": {
                            "propertyOrder": 3,
                            "type": "string"
                        },
                        "adsVersion": {
                            "propertyOrder": 8,
                            "type": "string"
                        },
                        "adsVersionBuild": {
                            "minimum": 0,
                            "propertyOrder": 9,
                            "type": "integer",
                            "visibility": "HideInEngineering"
                        },
                        "connectionState": {
                            "propertyOrder": 1,
                            "type": "string"
                        },
                        "deviceName": {
                            "propertyOrder": 4,
                            "type": "string"
                        },
                        "isUserModeRuntime": {
                            "propertyOrder": 10,
                            "type": "boolean",
                            "visibility": "HideInEngineering"
                        },
                        "systemServiceAdsState": {
                            "propertyOrder": 2,
                            "type": "string"
                        }
                    },
                    "required": [
                        "deviceName",
                        "adsVersion",
                        "adsState",
                        "connectionState"
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
