# List all registered Speech Services and HMI Clients.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSpeech"` |
| Full symbol path | `"TcHmiSpeech.Clients.List"` |
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
            "symbol": "TcHmiSpeech.Clients.List"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSpeech.Clients.List', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSpeech.Clients.List=' +
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
            "$ref": "#/definitions/SpeechClientEntry"
        },
        "type": "array"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
