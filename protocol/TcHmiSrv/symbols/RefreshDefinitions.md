# Refresh all definitions of a particular type.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"RefreshDefinitions"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Refresh the 'project' definitions.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "RefreshDefinitions",
            "writeValue": "project"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Refresh the 'project' definitions.
```javascript
TcHmi.Server.writeSymbol('RefreshDefinitions',
    "project",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'RefreshDefinitions=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true
    },
    "writeValue": {
        "enum": [
            "framework",
            "project",
            "general"
        ],
        "type": "string"
    }
}
```
