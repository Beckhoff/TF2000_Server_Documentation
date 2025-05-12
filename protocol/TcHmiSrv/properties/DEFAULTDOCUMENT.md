# This default page is served when a web client requests a URL that points to a directory structure instead of an actual web page within the directory structure.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::DEFAULTDOCUMENT"` |
| Category | webserver |
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
            "symbol": "TcHmiSrv.Config::DEFAULTDOCUMENT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFAULTDOCUMENT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFAULTDOCUMENT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"array"` |
| Unique items | Yes |
| Implicit access is allowed | Yes |

## Default value

```json
[
    "Default.html"
]
```

## JSON schema

```json
{
    "category": "webserver",
    "default": [
        "Default.html"
    ],
    "items": {
        "format": "filename",
        "type": "string"
    },
    "type": "array",
    "uniqueItems": true
}
```
