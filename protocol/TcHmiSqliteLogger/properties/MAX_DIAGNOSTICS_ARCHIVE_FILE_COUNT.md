# Server restart required.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Full symbol path | `"TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT"` |
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
            "symbol": "TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `1` |
| Maximum | `16` |
| Implicit access is allowed | Yes |
| Default value | `2` |

## JSON schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/UINT32"
        },
        {
            "configDescription": "DESC_MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT",
            "default": 2,
            "maximum": 16,
            "minimum": 1,
            "visibility": "HideInEngineering"
        }
    ]
}
```
