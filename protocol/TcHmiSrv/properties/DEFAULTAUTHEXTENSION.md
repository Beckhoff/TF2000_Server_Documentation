# Multiple authentication extensions can be used at the same time. The default authentication extension is automatically selected on the login page.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::DEFAULTAUTHEXTENSION"` |
| Category | security |
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
            "symbol": "TcHmiSrv.Config::DEFAULTAUTHEXTENSION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFAULTAUTHEXTENSION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFAULTAUTHEXTENSION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Implicit access is allowed | Yes |
| Default value | `"TcHmiUserManagement"` |

## JSON schema

```json
{
    "category": "security",
    "default": "TcHmiUserManagement",
    "optionMethod": {
        "filter": [
            {
                "comparator": "==",
                "path": "authExtension",
                "value": true
            }
        ],
        "symbol": "ListDomains"
    },
    "type": "string"
}
```
