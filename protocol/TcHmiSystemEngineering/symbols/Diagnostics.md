# Get information about the connections between the HMI server and the ADS targets.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSystemEngineering"` |
| Full symbol path | `"TcHmiSystemEngineering.Diagnostics"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSystemEngineering.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSystemEngineering.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSystemEngineering.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "additionalProperties": {
            "properties": {
                "adsRuntime": {
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
                "state": {
                    "type": "string"
                },
                "symbolInitState": {
                    "type": "string"
                },
                "symbolInitialized": {
                    "type": "boolean"
                },
                "symbolUpdateError": {
                    "properties": {
                        "code": {
                            "type": "string"
                        },
                        "message": {
                            "type": "string"
                        }
                    },
                    "type": "object"
                },
                "symbolUpdateStateDesc": {
                    "type": "string"
                },
                "symbolsUpToDate": {
                    "type": "boolean"
                }
            },
            "type": "object"
        },
        "function": true,
        "readOnly": true,
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
