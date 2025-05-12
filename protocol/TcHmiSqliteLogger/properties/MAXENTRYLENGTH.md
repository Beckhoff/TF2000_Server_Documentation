# Entries that exceed this limit will be truncated before being stored.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Full symbol path | `"TcHmiSqliteLogger.Config::MAXENTRYLENGTH"` |
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
            "symbol": "TcHmiSqliteLogger.Config::MAXENTRYLENGTH"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Config::MAXENTRYLENGTH', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Config::MAXENTRYLENGTH=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `80` |
| Implicit access is allowed | Yes |
| Default value | `1024` |

## JSON schema

```json
{
    "configDescription": "DESC_MAXENTRYLENGTH",
    "default": 1024,
    "minimum": 80,
    "type": "integer",
    "unit": "byte"
}
```
