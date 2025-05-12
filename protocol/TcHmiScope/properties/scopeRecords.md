# Scope records.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.Config::scopeRecords"` |
| Visibility | HideInEngineering |
| Contained in every configuration by default | No |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.Config::scopeRecords"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiScope.Config::scopeRecords', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiScope.Config::scopeRecords=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"array"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "items": {
        "properties": {
            "headlessServer": {
                "type": "string"
            },
            "headlessServerConnectionId": {
                "type": "string"
            },
            "scopeConfigName": {
                "type": "string"
            },
            "serverHandles": {
                "items": {
                    "properties": {
                        "guid": {
                            "type": "string"
                        },
                        "serverHandle": {
                            "type": "integer"
                        }
                    },
                    "required": [
                        "guid",
                        "serverHandle"
                    ],
                    "type": "object"
                },
                "type": "array"
            },
            "targetConnectionIds": {
                "items": {
                    "properties": {
                        "connectionId": {
                            "type": "integer"
                        },
                        "target": {
                            "type": "string"
                        },
                        "targetNetId": {
                            "type": "string"
                        }
                    },
                    "required": [
                        "connectionId",
                        "target",
                        "targetNetId"
                    ],
                    "type": "object"
                },
                "type": "array"
            },
            "triggerHandles": {
                "items": {
                    "properties": {
                        "clientTriggerHandle": {
                            "type": "integer"
                        },
                        "groupHandle": {
                            "type": "integer"
                        },
                        "guid": {
                            "type": "string"
                        }
                    },
                    "required": [
                        "guid",
                        "groupHandle",
                        "clientTriggerHandle"
                    ],
                    "type": "object"
                },
                "type": "array"
            }
        },
        "required": [
            "scopeConfigName",
            "headlessServerConnectionId",
            "serverHandles",
            "triggerHandles",
            "targetConnectionIds"
        ],
        "type": "object"
    },
    "readOnly": true,
    "type": "array",
    "visibility": "HideInEngineering"
}
```
