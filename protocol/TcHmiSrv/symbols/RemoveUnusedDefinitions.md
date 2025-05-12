# Removes all server definitions that are not used by any mapped symbol.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"RemoveUnusedDefinitions"` |
| Category | symbols |
| Visibility | AlwaysShow |

## Sample request - WebSocket

List all unused definitions except 'PLC1.REAL64'
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "RemoveUnusedDefinitions",
            "writeValue": {
                "dryRun": true,
                "ignore": [
                    "PLC1.REAL64"
                ]
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

List all unused definitions except 'PLC1.REAL64'
```javascript
TcHmi.Server.writeSymbol('RemoveUnusedDefinitions',
    {
        "dryRun": true,
        "ignore": [
            "PLC1.REAL64"
        ]
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
            'RemoveUnusedDefinitions=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "symbols",
    "readValue": {
        "function": true,
        "items": [
            {
                "type": "string"
            }
        ],
        "type": "array"
    },
    "writeValue": {
        "anyOf": [
            {
                "properties": {
                    "dryRun": {
                        "default": false,
                        "type": "boolean"
                    },
                    "ignore": {
                        "default": [],
                        "items": {
                            "type": "string"
                        },
                        "type": "array",
                        "uniqueItems": true
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
