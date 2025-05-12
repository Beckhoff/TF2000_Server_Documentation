# Confirm the given alarm.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ConfirmAlarm"` |
| Kategorie | events |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Confirm a specific active alarm.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ConfirmAlarm",
            "writeValue": {
                "alarmState": 2,
                "confirmationState": 2,
                "domain": "EventSystem",
                "id": 3,
                "name": "ALARM_TO_CONFIRM",
                "params": {},
                "severity": 1,
                "timeCleared": "2020-12-28T10:32:23.2066268Z",
                "timeConfirmed": null,
                "timeRaised": "2020-12-28T10:32:23.2066268Z"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Confirm a specific active alarm.
```javascript
TcHmi.Server.writeSymbol('ConfirmAlarm',
    {
        "alarmState": 2,
        "confirmationState": 2,
        "domain": "EventSystem",
        "id": 3,
        "name": "ALARM_TO_CONFIRM",
        "params": {},
        "severity": 1,
        "timeCleared": "2020-12-28T10:32:23.2066268Z",
        "timeConfirmed": null,
        "timeRaised": "2020-12-28T10:32:23.2066268Z"
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
            'ConfirmAlarm=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "events",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "$ref": "tchmi:server#/definitions/alarm"
    }
}
```
