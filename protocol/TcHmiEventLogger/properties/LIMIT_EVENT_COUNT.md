# Active alarms are always imported, even if this limit is exceeded as a result.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Full symbol path | `"TcHmiEventLogger.Config::LIMIT_EVENT_COUNT"` |
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
            "symbol": "TcHmiEventLogger.Config::LIMIT_EVENT_COUNT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEventLogger.Config::LIMIT_EVENT_COUNT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEventLogger.Config::LIMIT_EVENT_COUNT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `0` |
| Maximum | `4294967295` |
| Implicit access is allowed | Yes |
| Default value | `1000` |

## JSON schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/UINT32"
        },
        {
            "configDescription": "DESC_LIMIT_EVENT_COUNT",
            "default": 1000
        }
    ]
}
```
