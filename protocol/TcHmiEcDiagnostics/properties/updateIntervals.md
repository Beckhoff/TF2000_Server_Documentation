# Minimum time between two asynchronous requests for each request.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.Config::updateIntervals"` |
| Visibility | AlwaysShow |
| Contained in every configuration by default | No |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.Config::updateIntervals"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEcDiagnostics.Config::updateIntervals', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEcDiagnostics.Config::updateIntervals=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "properties": {
        "MasterList": {
            "default": 1000,
            "description": "Minimum time between two requests in ms.",
            "type": "integer"
        },
        "MasterOnlineInfo": {
            "default": 300,
            "description": "Including frame statistic (sent frames, damaged frames, lost frames, ...) and master state.",
            "type": "integer"
        },
        "ProcessDataValues": {
            "default": 1000,
            "type": "integer"
        },
        "Slaves": {
            "default": 1000,
            "type": "integer"
        },
        "SlavesOnlineInfo": {
            "default": 1000,
            "type": "integer"
        }
    },
    "required": [
        "MasterList",
        "MasterOnlineInfo",
        "Slaves",
        "SlavesOnlineInfo",
        "ProcessDataValues"
    ],
    "type": "object"
}
```
