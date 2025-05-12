# Downloaded files will be split into chunks of this size.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::CHUNKSIZE"` |
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
            "symbol": "TcHmiSrv.Config::CHUNKSIZE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::CHUNKSIZE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::CHUNKSIZE=' +
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
            "configDescription": "DESC_CHUNKSIZE",
            "default": 1048576,
            "unit": "byte"
        }
    ]
}
```
