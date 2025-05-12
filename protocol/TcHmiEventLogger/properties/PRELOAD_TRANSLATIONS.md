# Improve latency of the event import by reducing the number of network roundtrips for localization.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Full symbol path | `"TcHmiEventLogger.Config::PRELOAD_TRANSLATIONS"` |
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
            "symbol": "TcHmiEventLogger.Config::PRELOAD_TRANSLATIONS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEventLogger.Config::PRELOAD_TRANSLATIONS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEventLogger.Config::PRELOAD_TRANSLATIONS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"boolean"` |
| Implicit access is allowed | Yes |
| Default value | `False` |

## JSON schema

```json
{
    "configDescription": "DESC_PRELOAD_TRANSLATIONS",
    "default": false,
    "type": "boolean"
}
```
