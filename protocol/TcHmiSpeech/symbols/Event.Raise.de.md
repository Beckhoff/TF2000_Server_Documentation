# Raise an event.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSpeech"` |
| Vollständiger Symbol-Pfad | `"TcHmiSpeech.Event.Raise"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Raise a test event.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSpeech.Event.Raise",
            "writeValue": {
                "Command": {
                    "DetectedCommand": "bla",
                    "Parameter": {
                        "test": true
                    }
                },
                "RemoteSocketId": 58,
                "SocketId": 58,
                "SpeechApiVersion": 1
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Raise a test event.
```javascript
TcHmi.Server.writeSymbol('TcHmiSpeech.Event.Raise',
    {
        "Command": {
            "DetectedCommand": "bla",
            "Parameter": {
                "test": true
            }
        },
        "RemoteSocketId": 58,
        "SocketId": 58,
        "SpeechApiVersion": 1
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
            'TcHmiSpeech.Event.Raise=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "$ref": "#/definitions/SpeechPayloadContainer"
    }
}
```
