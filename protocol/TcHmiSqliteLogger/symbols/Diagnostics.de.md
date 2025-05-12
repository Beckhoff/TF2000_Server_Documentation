# Get information about the amount of data that is currently in the database.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteLogger.Diagnostics"` |
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
            "symbol": "TcHmiSqliteLogger.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "allDomains": {
                "properties": {
                    "databaseSize": {
                        "allOf": [
                            {
                                "$ref": "tchmi:general#/definitions/INT64"
                            },
                            {
                                "propertyOrder": 1,
                                "unit": "byte"
                            }
                        ]
                    },
                    "numEvents": {
                        "propertyOrder": 3,
                        "type": "integer"
                    },
                    "numEventsWithAlarmPayload": {
                        "propertyOrder": 7,
                        "type": "integer"
                    },
                    "numEventsWithMessagePayload": {
                        "propertyOrder": 5,
                        "type": "integer"
                    },
                    "numPersistentEvents": {
                        "propertyOrder": 4,
                        "type": "integer",
                        "visibility": "HideInEngineering"
                    },
                    "numPersistentEventsWithAlarmPayload": {
                        "propertyOrder": 8,
                        "type": "integer",
                        "visibility": "HideInEngineering"
                    },
                    "numPersistentEventsWithMessagePayload": {
                        "propertyOrder": 6,
                        "type": "integer",
                        "visibility": "HideInEngineering"
                    },
                    "persistentDatabaseSize": {
                        "allOf": [
                            {
                                "$ref": "tchmi:general#/definitions/INT64"
                            },
                            {
                                "propertyOrder": 2,
                                "unit": "byte"
                            }
                        ]
                    }
                },
                "required": [
                    "databaseSize",
                    "persistentDatabaseSize",
                    "numEvents",
                    "numPersistentEvents",
                    "numEventsWithMessagePayload",
                    "numPersistentEventsWithMessagePayload",
                    "numEventsWithAlarmPayload",
                    "numPersistentEventsWithAlarmPayload"
                ],
                "type": "object"
            },
            "perDomain": {
                "additionalProperties": {
                    "properties": {
                        "numEvents": {
                            "propertyOrder": 1,
                            "type": "integer"
                        },
                        "numEventsWithAlarmPayload": {
                            "propertyOrder": 5,
                            "type": "integer"
                        },
                        "numEventsWithMessagePayload": {
                            "propertyOrder": 3,
                            "type": "integer"
                        },
                        "numPersistentEvents": {
                            "propertyOrder": 2,
                            "type": "integer",
                            "visibility": "HideInEngineering"
                        },
                        "numPersistentEventsWithAlarmPayload": {
                            "propertyOrder": 6,
                            "type": "integer",
                            "visibility": "HideInEngineering"
                        },
                        "numPersistentEventsWithMessagePayload": {
                            "propertyOrder": 4,
                            "type": "integer",
                            "visibility": "HideInEngineering"
                        }
                    },
                    "required": [
                        "numEvents",
                        "numPersistentEvents",
                        "numEventsWithMessagePayload",
                        "numPersistentEventsWithMessagePayload",
                        "numEventsWithAlarmPayload",
                        "numPersistentEventsWithAlarmPayload"
                    ],
                    "type": "object"
                },
                "type": "object"
            }
        },
        "required": [
            "allDomains",
            "perDomain"
        ],
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
