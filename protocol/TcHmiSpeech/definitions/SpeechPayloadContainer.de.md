# SpeechPayloadContainer

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSpeech"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "additionalProperties": false,
    "properties": {
        "Command": {
            "type": "object"
        },
        "RemoteSocketId": {
            "description": "Socket id of the remote client in the server.",
            "type": "integer"
        },
        "SocketId": {
            "description": "Socket id of the client in the server.",
            "type": "integer"
        },
        "SpeechApiVersion": {
            "type": "integer"
        }
    },
    "required": [
        "SpeechApiVersion",
        "SocketId",
        "RemoteSocketId",
        "Command"
    ],
    "type": "object"
}
```
