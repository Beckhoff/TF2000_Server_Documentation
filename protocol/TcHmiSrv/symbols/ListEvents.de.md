# List currently active alarms.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ListEvents"` |
| Kategorie | events |
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
            "symbol": "ListEvents"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

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

## JSON-Schema

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
