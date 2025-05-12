# Shorter validity durations limit the damage from key compromise and mis-issuance. Stolen keys and mis-issued certificates are valid for a shorter period of time.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::CERTIFICATEEXPIRATION"` |
| Category | security |
| Visibility | HideInEngineering |
| Contained in every configuration by default | Yes |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSrv.Config::CERTIFICATEEXPIRATION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::CERTIFICATEEXPIRATION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::CERTIFICATEEXPIRATION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | timespan |
| Implicit access is allowed | Yes |
| Default value | `"P14000D"` |

## JSON schema

```json
{
    "category": "security",
    "default": "P14000D",
    "defaultConfigurable": true,
    "format": "timespan",
    "type": "string",
    "visibility": "HideInEngineering"
}
```
