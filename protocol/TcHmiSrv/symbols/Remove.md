# Remove array entry.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"Remove"` |
| Category | configurationsAndFilesystem |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| domain | string | Extension domain. |
| configuration | string | Configuration name. |
| path | string | Path to the entry. |
| value |  |  |

## Sample request - WebSocket

Remove all entries with value `5`
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Remove",
            "writeValue": {
                "domain": "Simulation",
                "path": "test",
                "value": 5
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Remove all entries with value `5`
```javascript
TcHmi.Server.writeSymbol('Remove',
    {
        "domain": "Simulation",
        "path": "test",
        "value": 5
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
            'Remove=' +
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
            "configuration": {
                "default": "default",
                "description": "Configuration name.",
                "type": "string"
            },
            "domain": {
                "description": "Extension domain.",
                "type": "string"
            },
            "path": {
                "description": "Path to the entry.",
                "type": "string"
            },
            "value": {}
        },
        "required": [
            "path",
            "domain",
            "value"
        ],
        "type": "object"
    }
}
```
