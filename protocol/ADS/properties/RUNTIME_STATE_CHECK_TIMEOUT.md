# A configured runtime is considered unreachable if a request takes longer than this timeout.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.Config::RUNTIME_STATE_CHECK_TIMEOUT"` |
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
            "symbol": "ADS.Config::RUNTIME_STATE_CHECK_TIMEOUT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::RUNTIME_STATE_CHECK_TIMEOUT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::RUNTIME_STATE_CHECK_TIMEOUT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | timespan |
| Minimum | `PT1S` |
| Maximum | `PT30S` |
| Implicit access is allowed | Yes |
| Default value | `"PT5S"` |

## JSON schema

```json
{
    "default": "PT5S",
    "format": "timespan",
    "formatMaximum": "PT30S",
    "formatMinimum": "PT1S",
    "propertyOrder": 3,
    "type": "string",
    "visibility": "HideInEngineering"
}
```
