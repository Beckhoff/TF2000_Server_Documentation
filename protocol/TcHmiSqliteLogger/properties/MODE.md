# Synchronous off mode is fast but can corrupt the database in case of a power failure.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Full symbol path | `"TcHmiSqliteLogger.Config::MODE"` |
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
            "symbol": "TcHmiSqliteLogger.Config::MODE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Config::MODE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Config::MODE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |
| Default value | `1` |

## Options

| Value | Label |
| ----- | ----- |
| `0` | Synchronous extra |
| `1` | Synchronous full |
| `3` | Synchronous normal |
| `4` | Synchronous off |

## JSON schema

```json
{
    "configDescription": "DESC_MODE",
    "default": 1,
    "enum": [
        0,
        1,
        3,
        4
    ],
    "options": [
        {
            "label": "ENUM_SYNCHRONOUS_EXTRA_PERSIST",
            "value": 0
        },
        {
            "label": "ENUM_SYNCHRONOUS_FULL_PERSIST",
            "value": 1
        },
        {
            "label": "ENUM_SYNCHRONOUS_NORMAL_PERSIST",
            "value": 3
        },
        {
            "label": "ENUM_SYNCHRONOUS_OFF_PERSIST",
            "value": 4
        }
    ],
    "type": "integer",
    "visibility": "HideInEngineering"
}
```
