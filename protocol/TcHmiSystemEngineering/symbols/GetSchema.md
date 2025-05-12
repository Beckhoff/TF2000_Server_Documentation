# Get the schema of a specific dynamic symbol.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSystemEngineering"` |
| Full symbol path | `"TcHmiSystemEngineering.GetSchema"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Get the JSON schema of a specific variable of the 'PLC1' runtime.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSystemEngineering.GetSchema",
            "writeValue": "PLC1::MAIN::nCounter"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get the JSON schema of a specific variable of the 'PLC1' runtime.
```javascript
TcHmi.Server.writeSymbol('TcHmiSystemEngineering.GetSchema',
    "PLC1::MAIN::nCounter",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiSystemEngineering.GetSchema=' +
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
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
