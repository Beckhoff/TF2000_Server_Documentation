# A stricter synchronization mode lowers the chance that the database is corrupted in case of a crash or power failure. The memory journaling mode can also corrupt the database.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Full symbol path | `"TcHmiSqliteHistorize.Config::mode"` |
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
            "symbol": "TcHmiSqliteHistorize.Config::mode"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteHistorize.Config::mode', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteHistorize.Config::mode=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Enumeration type | `"integer"` |
| Implicit access is allowed | Yes |
| Default value | `3` |

## Options

| Value | Label |
| ----- | ----- |
| `0` | Synchronous extra, journal mode persist |
| `1` | Synchronous full, journal mode persist |
| `2` | Synchronous full, journal mode memory |
| `3` | Synchronous normal, journal mode persist |
| `4` | Synchronous off, journal mode persist |
| `5` | Synchronous off, journal mode memory |

## JSON schema

```json
{
    "configDescription": "descMode",
    "default": 3,
    "enum": [
        0,
        1,
        2,
        3,
        4,
        5
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
            "label": "ENUM_SYNCHRONOUS_FULL_MEMORY",
            "value": 2
        },
        {
            "label": "ENUM_SYNCHRONOUS_NORMAL_PERSIST",
            "value": 3
        },
        {
            "label": "ENUM_SYNCHRONOUS_OFF_PERSIST",
            "value": 4
        },
        {
            "label": "ENUM_SYNCHRONOUS_OFF_MEMORY",
            "value": 5
        }
    ],
    "propertyOrder": 7,
    "type": "integer",
    "visibility": "HideInEngineering"
}
```
