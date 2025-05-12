# For security reasons, this error output should be disabled.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLua"` |
| Full symbol path | `"TcHmiLua.Config::HTML_ERRORS"` |
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
            "symbol": "TcHmiLua.Config::HTML_ERRORS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLua.Config::HTML_ERRORS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLua.Config::HTML_ERRORS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"boolean"` |
| Implicit access is allowed | Yes |
| Default value | `False` |

## JSON schema

```json
{
    "configDescription": "DESC_HTML_ERRORS",
    "default": false,
    "type": "boolean"
}
```
