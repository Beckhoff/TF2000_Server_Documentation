# List of mapped symbol names.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ListSymbolNames"` |
| Category | symbols |
| Visibility | AlwaysShow |

## Sample request - WebSocket

List the names of all mapped symbols of the TcHmiUserManagement domain.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListSymbolNames",
            "writeValue": {
                "domain": "TcHmiUserManagement"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

List the names of all mapped symbols of the TcHmiUserManagement domain.
```javascript
TcHmi.Server.writeSymbol('ListSymbolNames',
    {
        "domain": "TcHmiUserManagement"
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
            'ListSymbolNames=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "symbols",
    "readValue": {
        "description": "List of mapped symbol names.",
        "function": true,
        "items": {
            "type": "string"
        },
        "type": "array"
    },
    "writeValue": {
        "anyOf": [
            {
                "properties": {
                    "depth": {
                        "default": 1,
                        "maximum": 5,
                        "minimum": 1,
                        "type": "integer"
                    },
                    "domain": {
                        "type": "string"
                    },
                    "ignoreHiddenSymbols": {
                        "default": false,
                        "type": "boolean"
                    },
                    "onlyDynamicSymbols": {
                        "default": false,
                        "type": "boolean"
                    }
                },
                "type": "object"
            },
            {
                "$ref": "tchmi:general#/definitions/VOID"
            }
        ]
    }
}
```
