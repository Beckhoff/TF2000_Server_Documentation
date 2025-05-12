# Virtual directories are used to specify which folders paths on the file system should be served by the web server.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::VIRTUALDIRECTORIES"` |
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
            "symbol": "TcHmiSrv.Config::VIRTUALDIRECTORIES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::VIRTUALDIRECTORIES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::VIRTUALDIRECTORIES=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Minimum number of properties | 1 |
| Implicit access is allowed | Yes |

## Default value

```json
{
    "/": "www"
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "format": "filename",
        "type": "string"
    },
    "default": {
        "/": "www"
    },
    "defaultConfigurable": true,
    "minProperties": 1,
    "type": "object"
}
```
