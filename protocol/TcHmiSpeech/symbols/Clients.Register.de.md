# Register call for the Speech Service and Clients. ReadValue will include own SocketId.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSpeech"` |
| Vollständiger Symbol-Pfad | `"TcHmiSpeech.Clients.Register"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Register an additional Speech HMI Client.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSpeech.Clients.Register",
            "writeValue": {
                "AudioSink": true,
                "AudioSource": true,
                "CanAnswer": false,
                "CanOffer": true,
                "PotentialLocales": [
                    "de-DE",
                    "en"
                ],
                "RegisterDate": "2019-09-27T13:20:09.737Z",
                "RemoteSocketId": 0,
                "SocketId": 0,
                "SpeechApiVersion": 1,
                "State": "available",
                "Version": "Example version string"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Register an additional Speech HMI Client.
```javascript
TcHmi.Server.writeSymbol('TcHmiSpeech.Clients.Register',
    {
        "AudioSink": true,
        "AudioSource": true,
        "CanAnswer": false,
        "CanOffer": true,
        "PotentialLocales": [
            "de-DE",
            "en"
        ],
        "RegisterDate": "2019-09-27T13:20:09.737Z",
        "RemoteSocketId": 0,
        "SocketId": 0,
        "SpeechApiVersion": 1,
        "State": "available",
        "Version": "Example version string"
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
            'TcHmiSpeech.Clients.Register=' +
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
        "$ref": "#/definitions/SpeechClientEntry"
    }
}
```
