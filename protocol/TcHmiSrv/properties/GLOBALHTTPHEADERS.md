# These headers will be added to all HTTP responses.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::GLOBALHTTPHEADERS"` |
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
            "symbol": "TcHmiSrv.Config::GLOBALHTTPHEADERS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::GLOBALHTTPHEADERS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::GLOBALHTTPHEADERS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | multiline |
| Implicit access is allowed | Yes |

## Default value

```txt
{LASTMODIFIED}
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type-Options: nosniff
```

## JSON schema

```json
{
    "category": "webserver",
    "configDescription": "DESC_GLOBAL_HTTP_HEADERS",
    "default": "{LASTMODIFIED}\nStrict-Transport-Security: max-age=31536000; includeSubDomains\nX-Content-Type-Options: nosniff",
    "format": "multiline",
    "type": "string"
}
```
