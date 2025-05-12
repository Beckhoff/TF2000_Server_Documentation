# Multiple authentication extensions can be used at the same time. The default authentication extension is automatically selected on the login page.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"DefaultAuthExtension"` |
| Category | security |
| Visibility | AlwaysShow |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "DefaultAuthExtension",
            "writeValue": "TcHmiUserManagement"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.writeSymbol('DefaultAuthExtension',
    "TcHmiUserManagement",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'DefaultAuthExtension=' +
            data.response.commands[0].readValue);
    }
);
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
    "readValue": {
        "default": "TcHmiUserManagement",
        "type": "string"
    }
}
```
