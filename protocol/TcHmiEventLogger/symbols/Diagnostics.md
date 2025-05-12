# Get information about the connections between the HMI serer and the configured target systems.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Full symbol path | `"TcHmiEventLogger.Diagnostics"` |
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
            "symbol": "TcHmiEventLogger.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEventLogger.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEventLogger.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "TARGET_SYSTEMS": {
                "additionalProperties": {
                    "properties": {
                        "activeAlarmsCount": {
                            "propertyOrder": 10,
                            "type": "integer"
                        },
                        "cachedAlarmsCount": {
                            "propertyOrder": 8,
                            "type": "integer",
                            "visibility": "HideInEngineering"
                        },
                        "cachedInvalidAlarmsCount": {
                            "propertyOrder": 9,
                            "type": "integer",
                            "visibility": "HideInEngineering"
                        },
                        "cachedMessagesCount": {
                            "propertyOrder": 7,
                            "type": "integer",
                            "visibility": "HideInEngineering"
                        },
                        "connectError": {
                            "propertyOrder": 2,
                            "type": "string"
                        },
                        "connectionState": {
                            "propertyOrder": 1,
                            "type": "string"
                        },
                        "importedAlarmsCount": {
                            "propertyOrder": 5,
                            "type": "integer"
                        },
                        "importedEventsCount": {
                            "propertyOrder": 3,
                            "type": "integer"
                        },
                        "importedInvalidAlarmsCount": {
                            "propertyOrder": 6,
                            "type": "integer"
                        },
                        "importedMessagesCount": {
                            "propertyOrder": 4,
                            "type": "integer"
                        }
                    },
                    "required": [
                        "connectionState"
                    ],
                    "type": "object"
                },
                "description": "DESC_TARGET_SYSTEM",
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
