# Compare the schema of all mapped symbols with the schema of the part of the symbol tree they are mapped to. Return all mapped symbols for which these schemas differ.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ListOutdatedSymbols"` |
| Category | symbols |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Do the comparison for all mapped symbols from the 'ADS' domain.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListOutdatedSymbols",
            "writeValue": {
                "domain": "ADS",
                "ignoreHiddenSymbols": false,
                "onlyDynamicSymbols": true
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Do the comparison for all mapped symbols from the 'ADS' domain.
```javascript
TcHmi.Server.writeSymbol('ListOutdatedSymbols',
    {
        "domain": "ADS",
        "ignoreHiddenSymbols": false,
        "onlyDynamicSymbols": true
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
            'ListOutdatedSymbols=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "symbols",
    "readValue": {
        "additionalProperties": {
            "enum": [
                "SYMBOL_SCHEMA_DIFFERENCE",
                "SYMBOL_INVALID_DOMAIN",
                "SYMBOL_INVALID_SYMBOL"
            ],
            "type": "string"
        },
        "function": true,
        "type": "object"
    },
    "writeValue": {
        "anyOf": [
            {
                "properties": {
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
