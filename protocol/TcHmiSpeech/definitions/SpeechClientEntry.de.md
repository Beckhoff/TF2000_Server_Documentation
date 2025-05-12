# SpeechClientEntry

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
        "AudioSink": {
            "description": "This client can consume an audio stream.",
            "type": "boolean"
        },
        "AudioSource": {
            "description": "This client can provide an audio source.",
            "type": "boolean"
        },
        "CanAnswer": {
            "description": "This client can answer an WebRTC call.",
            "type": "boolean"
        },
        "CanOffer": {
            "description": "This client can start an WebRTC call.",
            "type": "boolean"
        },
        "PotentialLocales": {
            "description": "A list of all Locales the client can be set to.",
            "items": {
                "$ref": "tchmi:general#/definitions/Locale"
            },
            "type": "array"
        },
        "RegisterDate": {
            "$ref": "tchmi:general#/definitions/DateTime"
        },
        "RemoteSocketId": {
            "description": "Socket id of the remote client in the server. Unused in this command.",
            "type": "integer"
        },
        "SocketId": {
            "description": "Socket id of the client in the server.",
            "type": "integer"
        },
        "SpeechApiVersion": {
            "type": "integer"
        },
        "State": {
            "enum": [
                "available",
                "busy",
                "offline"
            ],
            "type": "string"
        },
        "Version": {
            "description": "Version string of the client.",
            "type": "string"
        }
    },
    "required": [
        "SpeechApiVersion",
        "RegisterDate",
        "SocketId",
        "RemoteSocketId",
        "AudioSink",
        "AudioSource",
        "CanOffer",
        "CanAnswer",
        "Version",
        "PotentialLocales",
        "State"
    ],
    "type": "object"
}
```
