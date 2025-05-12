# List all clientConfigs of the current HMI states.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSpeech"` |
| Vollständiger Symbol-Pfad | `"TcHmiSpeech.ClientConfigs.List"` |
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
            "symbol": "TcHmiSpeech.ClientConfigs.List"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

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
| Typ | `"array"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

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
