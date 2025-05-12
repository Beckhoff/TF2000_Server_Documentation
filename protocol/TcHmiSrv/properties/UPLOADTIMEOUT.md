# Upload requests will be rejected if they do not succeed after this duration.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::UPLOADTIMEOUT"` |
| Category | advanced |
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
            "symbol": "TcHmiSrv.Config::UPLOADTIMEOUT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::UPLOADTIMEOUT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::UPLOADTIMEOUT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | timespan |
| Minimum | `PT1S` |
| Implicit access is allowed | Yes |
| Default value | `"PT20S"` |

## JSON schema

```json
{
    "category": "advanced",
    "default": "PT20S",
    "format": "timespan",
    "formatMinimum": "PT1S",
    "type": "string"
}
```
