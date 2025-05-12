# If this value is reached, the events will be displayed on several pages

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLua"` |
| Full symbol path | `"TcHmiLua.Config::LOG_PAGE_MAX_ENTRIES"` |
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
            "symbol": "TcHmiLua.Config::LOG_PAGE_MAX_ENTRIES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLua.Config::LOG_PAGE_MAX_ENTRIES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLua.Config::LOG_PAGE_MAX_ENTRIES=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `10` |
| Implicit access is allowed | Yes |
| Default value | `200` |

## JSON schema

```json
{
    "configDescription": "DESC_LOG_PAGE_MAX_ENTRIES",
    "default": 200,
    "minimum": 10,
    "type": "integer"
}
```
