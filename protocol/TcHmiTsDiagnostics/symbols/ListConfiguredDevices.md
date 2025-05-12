# Get a list of all configured EtherCAT devices.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Full symbol path | `"TcHmiTsDiagnostics.ListConfiguredDevices"` |
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
            "symbol": "TcHmiTsDiagnostics.ListConfiguredDevices"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiTsDiagnostics.ListConfiguredDevices', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiTsDiagnostics.ListConfiguredDevices=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "additionalProperties": {
            "properties": {
                "enabled": {
                    "type": "boolean"
                },
                "masterNetId": {
                    "format": "amsnetid",
                    "type": "string"
                },
                "targetNetId": {
                    "format": "amsnetid",
                    "type": "string"
                }
            },
            "required": [
                "enabled",
                "targetNetId",
                "masterNetId"
            ],
            "type": "object"
        },
        "function": true,
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
