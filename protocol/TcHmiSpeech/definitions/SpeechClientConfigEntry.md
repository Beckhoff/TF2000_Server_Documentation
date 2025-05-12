# Has a list of client config in the current HMI state

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
        "CurrentCommands": {
            "items": {
                "description": "Active command in the current HMI state",
                "type": "string"
            },
            "type": "array"
        },
        "CurrentLocales": {
            "items": {
                "allOf": [
                    {
                        "$ref": "tchmi:general#/definitions/Locale"
                    },
                    {
                        "description": "Current locales in the current HMI state"
                    }
                ]
            },
            "type": "array"
        },
        "RemoteSocketId": {
            "description": "Socket id of the remote client in the server.",
            "type": "integer"
        },
        "SocketId": {
            "description": "Socket id of the peer starting the signaling connection.",
            "type": "integer"
        },
        "SpeechApiVersion": {
            "type": "integer"
        }
    },
    "required": [
        "SocketId",
        "RemoteSocketId",
        "CurrentCommands",
        "CurrentLocales"
    ],
    "type": "object"
}
```
