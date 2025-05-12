# Get information about the connections between the HMI serer and the configured target systems.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiMdp"` |
| Full symbol path | `"TcHmiMdp.Diagnostics"` |
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
            "symbol": "TcHmiMdp.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiMdp.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiMdp.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "targetSystems": {
                "additionalProperties": {
                    "properties": {
                        "availableModulesCount": {
                            "propertyOrder": 4,
                            "type": "integer"
                        },
                        "connectError": {
                            "propertyOrder": 2,
                            "type": "integer"
                        },
                        "connectErrorMessage": {
                            "propertyOrder": 3,
                            "type": "string"
                        },
                        "connectionState": {
                            "propertyOrder": 1,
                            "type": "string"
                        }
                    },
                    "required": [
                        "connectionState"
                    ],
                    "type": "object"
                },
                "description": "descTargetSystems",
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
