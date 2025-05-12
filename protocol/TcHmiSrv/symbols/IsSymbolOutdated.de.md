# Compare the schema of a specific mapped symbol and the schema of the mapped part of the symbol tree.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"IsSymbolOutdated"` |
| Kategorie | symbols |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| symbol | string | Name of the symbol. |

## Beispiel-Anfrage - WebSocket

Do the comparison for the 'test1' symbol.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "IsSymbolOutdated",
            "writeValue": {
                "symbol": "test1"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Do the comparison for the 'test1' symbol.
```javascript
TcHmi.Server.writeSymbol('IsSymbolOutdated',
    {
        "symbol": "test1"
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
            'IsSymbolOutdated=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "symbols",
    "readValue": {
        "enum": [
            "SYMBOL_UP_TO_DATE",
            "SYMBOL_SCHEMA_DIFFERENCE",
            "SYMBOL_INVALID_DOMAIN",
            "SYMBOL_INVALID_SYMBOL"
        ],
        "function": true,
        "type": "string"
    },
    "writeValue": {
        "properties": {
            "symbol": {
                "description": "Name of the symbol.",
                "type": "string"
            }
        },
        "required": [
            "symbol"
        ],
        "type": "object"
    }
}
```
