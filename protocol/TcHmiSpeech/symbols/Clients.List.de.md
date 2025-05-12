# List all registered Speech Services and HMI Clients.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSpeech"` |
| Vollständiger Symbol-Pfad | `"TcHmiSpeech.Clients.List"` |
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
            "symbol": "TcHmiSpeech.Clients.List"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

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
| Typ | `"array"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

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
