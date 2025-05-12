# Minimum time between two asynchronous requests for each request.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Full symbol path | `"TcHmiTsDiagnostics.Config::updateIntervals"` |
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
            "symbol": "TcHmiTsDiagnostics.Config::updateIntervals"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiTsDiagnostics.Config::updateIntervals', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiTsDiagnostics.Config::updateIntervals=' +
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
        "OnlineData": {
            "default": 1000,
            "minimum": 1000,
            "type": "integer"
        },
        "Slaves": {
            "default": 1000,
            "type": "integer"
        }
    },
    "required": [
        "MasterList",
        "Slaves",
        "OnlineData"
    ],
    "type": "object"
}
```
