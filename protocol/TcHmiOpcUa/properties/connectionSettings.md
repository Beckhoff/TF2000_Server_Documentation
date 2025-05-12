# Connection details for the OPC-UA server

## General information

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |
| Full symbol path | `"TcHmiOpcUa.Config::connectionSettings"` |
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
            "symbol": "TcHmiOpcUa.Config::connectionSettings"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiOpcUa.Config::connectionSettings', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiOpcUa.Config::connectionSettings=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## Default value

```json
{
    "basic": {}
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "$ref": "#/definitions/connection"
    },
    "default": {
        "basic": {}
    },
    "type": "object"
}
```
