# Default timeout for ADS requests.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.Config::TIMEOUT"` |
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
            "symbol": "ADS.Config::TIMEOUT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::TIMEOUT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::TIMEOUT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | timespan |
| Minimum | `PT0.1S` |
| Implicit access is allowed | Yes |
| Default value | `"PT1S"` |

## JSON schema

```json
{
    "configDescription": "DESC_TIMEOUT",
    "default": "PT1S",
    "format": "timespan",
    "formatMinimum": "PT0.1S",
    "propertyOrder": 2,
    "type": "string"
}
```
