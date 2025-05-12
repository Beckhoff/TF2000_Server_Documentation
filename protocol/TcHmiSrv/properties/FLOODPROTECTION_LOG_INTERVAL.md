# Time to wait before creating the next 'request failed' log entry.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::FLOODPROTECTION_LOG_INTERVAL"` |
| Category | advanced |
| Visibility | HideInEngineering |
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
            "symbol": "TcHmiSrv.Config::FLOODPROTECTION_LOG_INTERVAL"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::FLOODPROTECTION_LOG_INTERVAL', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::FLOODPROTECTION_LOG_INTERVAL=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | timespan |
| Minimum | `PT2S` |
| Implicit access is allowed | Yes |
| Default value | `"PT1M"` |

## JSON schema

```json
{
    "category": "advanced",
    "configDescription": "DESC_FLOODPROTECTION_LOG_INTERVAL",
    "default": "PT1M",
    "format": "timespan",
    "formatMinimum": "PT2S",
    "type": "string",
    "visibility": "HideInEngineering"
}
```
