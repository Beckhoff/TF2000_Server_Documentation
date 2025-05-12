# Create or update an event.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"CreateEvent"` |
| Kategorie | events |
| Sichtbarkeit | AlwaysShow |

## Version 2.0

Since version 2.0, the default values for 'timeRaised' and 'timeReceived' are the current timestamp, not "1970-01-01T00:00:00Z".
## Beispiel-Anfrage - WebSocket

Create event with message payload.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "CreateEvent",
            "writeValue": {
                "domain": "TcHmiSrv",
                "name": "FILE_STORE",
                "payload": {
                    "domain": "TcHmiSrv",
                    "name": "FILE_STORE",
                    "params": {
                        "0": "test.txt"
                    },
                    "severity": 0
                },
                "payloadType": 0
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Create event with message payload.
```javascript
TcHmi.Server.writeSymbol('CreateEvent',
    {
        "domain": "TcHmiSrv",
        "name": "FILE_STORE",
        "payload": {
            "domain": "TcHmiSrv",
            "name": "FILE_STORE",
            "params": {
                "0": "test.txt"
            },
            "severity": 0
        },
        "payloadType": 0
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'CreateEvent=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "events",
    "readValue": {
        "function": true,
        "versions": [
            1.0,
            2.0
        ]
    },
    "versions": {
        "2.0": {
            "description": "Since version 2.0, the default values for 'timeRaised' and 'timeReceived' are the current timestamp, not \"1970-01-01T00:00:00Z\"."
        }
    },
    "writeValue": {
        "$ref": "tchmi:server#/definitions/event"
    }
}
```
