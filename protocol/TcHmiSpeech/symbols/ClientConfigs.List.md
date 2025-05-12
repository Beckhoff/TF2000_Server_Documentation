# List all clientConfigs of the current HMI states.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSpeech"` |
| Full symbol path | `"TcHmiSpeech.ClientConfigs.List"` |
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
            "symbol": "TcHmiSpeech.ClientConfigs.List"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSpeech.ClientConfigs.List', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSpeech.ClientConfigs.List=' +
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
    "readValue": {
        "items": {
            "$ref": "#/definitions/SpeechClientConfigEntry"
        },
        "type": "array"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
