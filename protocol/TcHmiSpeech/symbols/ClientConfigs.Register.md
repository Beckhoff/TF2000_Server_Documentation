# Register call for the clientConfig of the current HMI state.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSpeech"` |
| Full symbol path | `"TcHmiSpeech.ClientConfigs.Register"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Register a clientConfig of the current HMI state.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSpeech.ClientConfigs.Register",
            "writeValue": {
                "CurrentCommands": [
                    "newRegion42"
                ],
                "CurrentLocales": [
                    "de-DE"
                ],
                "RemoteSocketId": 23,
                "SocketId": 0,
                "SpeechApiVersion": 1
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Register a clientConfig of the current HMI state.
```javascript
TcHmi.Server.writeSymbol('TcHmiSpeech.ClientConfigs.Register',
    {
        "CurrentCommands": [
            "newRegion42"
        ],
        "CurrentLocales": [
            "de-DE"
        ],
        "RemoteSocketId": 23,
        "SocketId": 0,
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
            'TcHmiSpeech.ClientConfigs.Register=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "$ref": "#/definitions/SpeechClientConfigEntry"
    }
}
```
