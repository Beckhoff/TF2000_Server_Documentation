# Active alarms will always be imported, even if this limit is thereby exceeded.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiAlarm"` |
| Full symbol path | `"TcHmiAlarm.Config::limitEventCount"` |
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
            "symbol": "TcHmiAlarm.Config::limitEventCount"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiAlarm.Config::limitEventCount', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiAlarm.Config::limitEventCount=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `1` |
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
            "default": 1000,
            "minimum": 1,
            "propertyOrder": 1,
            "type": "integer"
        }
    ]
}
```
