# Server restart required.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Full symbol path | `"TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE"` |
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
            "symbol": "TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `10000` |
| Maximum | `4294967295` |
| Implicit access is allowed | Yes |
| Default value | `52428800` |

## JSON schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/UINT32"
        },
        {
            "configDescription": "DESC_MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE",
            "default": 52428800,
            "minimum": 10000,
            "unit": "byte",
            "visibility": "HideInEngineering"
        }
    ]
}
```
