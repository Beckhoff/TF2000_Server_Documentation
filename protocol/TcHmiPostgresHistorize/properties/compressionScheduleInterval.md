# Scheduled intervals for data compression 

## General information

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Full symbol path | `"TcHmiPostgresHistorize.Config::compressionScheduleInterval"` |
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
            "symbol": "TcHmiPostgresHistorize.Config::compressionScheduleInterval"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiPostgresHistorize.Config::compressionScheduleInterval', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiPostgresHistorize.Config::compressionScheduleInterval=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | timespan |
| Minimum | `PT30M` |
| Implicit access is allowed | Yes |
| Default value | `"P30D"` |

## JSON schema

```json
{
    "configDescription": "descCompressionScheduleInterval",
    "default": "P30D",
    "format": "timespan",
    "formatMinimum": "PT30M",
    "propertyOrder": 4,
    "type": "string"
}
```
