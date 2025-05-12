# Remove variable from configuration

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"RemoveFromConfiguration"` |
| Category | configurationsAndFilesystem |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| name | string | Name of the configuration. |
| domain | string | Domain of the config value. |
| path | string | Path of the config value. |

## Sample request - WebSocket

Remove files setting from CX9000 configuration
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "RemoveFromConfiguration",
            "writeValue": {
                "domain": "TcHmiSrv",
                "name": "CX9000",
                "path": "FILES"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Remove files setting from CX9000 configuration
```javascript
TcHmi.Server.writeSymbol('RemoveFromConfiguration',
    {
        "domain": "TcHmiSrv",
        "name": "CX9000",
        "path": "FILES"
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'RemoveFromConfiguration=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "configurationsAndFilesystem",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "properties": {
            "domain": {
                "description": "Domain of the config value.",
                "type": "string"
            },
            "name": {
                "description": "Name of the configuration.",
                "type": "string"
            },
            "path": {
                "description": "Path of the config value.",
                "type": "string"
            }
        },
        "required": [
            "name",
            "domain",
            "path"
        ],
        "type": "object"
    }
}
```
