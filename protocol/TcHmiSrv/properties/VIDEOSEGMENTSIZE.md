# HTTP range requests (streamed videos) will be split in chunks of this size.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::VIDEOSEGMENTSIZE"` |
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
            "symbol": "TcHmiSrv.Config::VIDEOSEGMENTSIZE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::VIDEOSEGMENTSIZE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::VIDEOSEGMENTSIZE=' +
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
| Default value | `1048576` |

## JSON schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/UINT32"
        },
        {
            "category": "advanced",
            "configDescription": "DESC_RANGE_REQUEST_SIZE",
            "default": 1048576,
            "unit": "byte"
        }
    ]
}
```
