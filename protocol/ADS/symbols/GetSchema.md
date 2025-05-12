# Get the schema of a specific dynamic symbol.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.GetSchema"` |
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
            "symbol": "ADS.GetSchema",
            "writeValue": "PLC1::MAIN::nCounter"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get the JSON schema of a specific variable of the 'PLC1' runtime.
```javascript
TcHmi.Server.writeSymbol('ADS.GetSchema',
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
            'ADS.GetSchema=' +
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
        "type": "string"
    }
}
```
