# Get PLC structure of specified runtime.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSystemEngineering"` |
| Full symbol path | `"TcHmiSystemEngineering.GetTreeView"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Get PLC structure of runtime 'Runtime1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSystemEngineering.GetTreeView",
            "writeValue": "Runtime1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get PLC structure of runtime 'Runtime1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiSystemEngineering.GetTreeView',
    "Runtime1",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiSystemEngineering.GetTreeView=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {},
        "readOnly": true,
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
