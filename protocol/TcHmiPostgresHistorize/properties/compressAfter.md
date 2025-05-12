# The interval of TimescaleDB's add_compression_policy determines the point in time from which data is compressed.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Full symbol path | `"TcHmiPostgresHistorize.Config::compressAfter"` |
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
            "symbol": "TcHmiPostgresHistorize.Config::compressAfter"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiPostgresHistorize.Config::compressAfter', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiPostgresHistorize.Config::compressAfter=' +
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
    "configDescription": "descCompressAfter",
    "default": "P30D",
    "format": "timespan",
    "formatMinimum": "PT30M",
    "propertyOrder": 3,
    "type": "string"
}
```
