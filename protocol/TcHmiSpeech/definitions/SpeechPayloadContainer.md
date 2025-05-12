# SpeechPayloadContainer

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSpeech"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

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
