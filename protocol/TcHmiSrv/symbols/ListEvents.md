# List currently active alarms.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ListEvents"` |
| Category | events |
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
            "symbol": "ListEvents"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ListEvents', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListEvents=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "events",
    "readValue": {
        "function": true,
        "items": {
            "oneOf": [
                {
                    "additionalProperties": false,
                    "properties": {
                        "domain": {
                            "type": "string"
                        },
                        "localizedString": {
                            "type": "string"
                        },
                        "name": {
                            "type": "string"
                        },
                        "payload": {
                            "oneOf": [
                                {
                                    "$ref": "tchmi:server#/definitions/alarm"
                                },
                                {
                                    "$ref": "tchmi:server#/definitions/message"
                                }
                            ]
                        },
                        "payloadType": {
                            "$ref": "tchmi:server#/definitions/eventType"
                        },
                        "sessionId": {
                            "type": "string"
                        },
                        "timeReceived": {
                            "format": "date-time",
                            "type": "string"
                        }
                    },
                    "required": [
                        "payload",
                        "payloadType",
                        "name",
                        "domain",
                        "timeReceived",
                        "localizedString"
                    ],
                    "type": "object"
                },
                {
                    "additionalProperties": false,
                    "properties": {
                        "domain": {
                            "type": "string"
                        },
                        "name": {
                            "type": "string"
                        },
                        "payload": {},
                        "payloadType": {
                            "$ref": "tchmi:server#/definitions/eventType"
                        },
                        "sessionId": {
                            "type": "string"
                        },
                        "timeReceived": {
                            "format": "date-time",
                            "type": "string"
                        }
                    },
                    "required": [
                        "name",
                        "domain",
                        "timeReceived"
                    ],
                    "type": "object"
                }
            ]
        },
        "type": "array"
    }
}
```
