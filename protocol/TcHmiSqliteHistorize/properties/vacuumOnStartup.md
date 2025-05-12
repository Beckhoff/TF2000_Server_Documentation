# Tries to reduce database size. This might take a while on big databases.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Full symbol path | `"TcHmiSqliteHistorize.Config::vacuumOnStartup"` |
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
            "symbol": "TcHmiSqliteHistorize.Config::vacuumOnStartup"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteHistorize.Config::vacuumOnStartup', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteHistorize.Config::vacuumOnStartup=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"boolean"` |
| Implicit access is allowed | Yes |
| Default value | `False` |

## JSON schema

```json
{
    "configDescription": "descVacuumOnStartup",
    "default": false,
    "propertyOrder": 5,
    "type": "boolean"
}
```
