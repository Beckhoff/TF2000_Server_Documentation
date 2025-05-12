# Get information about the alarms that are currently in the event database.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiAlarm"` |
| Vollständiger Symbol-Pfad | `"TcHmiAlarm.Diagnostics"` |
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
            "symbol": "TcHmiAlarm.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiAlarm.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiAlarm.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "activeAlarmsCount": {
                "propertyOrder": 7,
                "type": "integer"
            },
            "cachedAlarmsCount": {
                "propertyOrder": 5,
                "type": "integer"
            },
            "cachedInvalidAlarmsCount": {
                "propertyOrder": 6,
                "type": "integer"
            },
            "cachedMessagesCount": {
                "propertyOrder": 4,
                "type": "integer"
            },
            "database": {
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
                    "numEntries": {
                        "propertyOrder": 2,
                        "type": "integer"
                    }
                },
                "required": [
                    "databaseSize",
                    "numEntries"
                ],
                "type": "object"
            },
            "importedEventsCount": {
                "propertyOrder": 1,
                "type": "integer"
            },
            "importedInvalidAlarmsCount": {
                "propertyOrder": 3,
                "type": "integer"
            },
            "importedMessagesCount": {
                "propertyOrder": 2,
                "type": "integer"
            }
        },
        "required": [
            "importedEventsCount",
            "importedMessagesCount",
            "importedInvalidAlarmsCount",
            "cachedMessagesCount",
            "cachedAlarmsCount",
            "cachedInvalidAlarmsCount",
            "activeAlarmsCount",
            "database"
        ],
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
