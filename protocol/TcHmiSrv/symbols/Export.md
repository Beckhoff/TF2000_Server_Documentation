# Export a specific configuration. Requires access to the '*.Config' symbol of the requested domain.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"Export"` |
| Category | configurationsAndFilesystem |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| name | string |
| domain | string |
| full | boolean |

## Sample request - WebSocket

Export the ADS extension configuration for CX9000.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Export",
            "writeValue": {
                "domain": "ADS",
                "full": true,
                "name": "CX9000"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Export the ADS extension configuration for CX9000.
```javascript
TcHmi.Server.writeSymbol('Export',
    {
        "domain": "ADS",
        "full": true,
        "name": "CX9000"
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
            'Export=' +
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
                "type": "string"
            },
            "full": {
                "default": false,
                "type": "boolean"
            },
            "name": {
                "type": "string"
            }
        },
        "required": [
            "name",
            "domain"
        ],
        "type": "object"
    }
}
```
