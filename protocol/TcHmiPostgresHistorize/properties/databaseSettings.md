# PostgreSQL database settings

## General information

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Full symbol path | `"TcHmiPostgresHistorize.Config::databaseSettings"` |
| Category | Database settings |
| Visibility | AlwaysShow |
| Contained in every configuration by default | Yes |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiPostgresHistorize.Config::databaseSettings"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiPostgresHistorize.Config::databaseSettings', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiPostgresHistorize.Config::databaseSettings=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "category": "Database settings",
    "configDescription": "descDatabaseSettings",
    "defaultConfigurable": true,
    "properties": {
        "connectionString": {
            "configDescription": "descConnectionString",
            "default": "Server=localhost; Port=5432; Database=historize_postgres; Uid=postgres; Pwd=@{password};Timeout=10;",
            "format": "multiline",
            "type": "string"
        },
        "password": {
            "format": "masked",
            "propertyOrder": 5,
            "type": "string"
        },
        "tableId": {
            "configDescription": "descTableId",
            "default": 1,
            "propertyOrder": 7,
            "type": "number"
        }
    },
    "required": [
        "connectionString",
        "tableId",
        "password"
    ],
    "type": "object"
}
```
