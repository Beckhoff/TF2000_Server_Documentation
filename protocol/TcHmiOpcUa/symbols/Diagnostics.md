# Get information about the connections between the HMI server and the configured OPC-UA servers.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |
| Full symbol path | `"TcHmiOpcUa.Diagnostics"` |
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
            "symbol": "TcHmiOpcUa.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiOpcUa.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiOpcUa.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "diag_namespaces": {
                "additionalProperties": {
                    "properties": {
                        "available_ua_namespaces": {
                            "items": {
                                "type": "string"
                            },
                            "type": "array"
                        },
                        "list_symbols_state": {
                            "type": "string"
                        },
                        "name": {
                            "type": "string"
                        },
                        "state": {
                            "type": "string"
                        }
                    },
                    "type": "object"
                },
                "type": "object"
            }
        },
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
