# Remove array entry.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"Remove"` |
| Kategorie | configurationsAndFilesystem |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| domain | string | Extension domain. |
| configuration | string | Configuration name. |
| path | string | Path to the entry. |
| value |  |  |

## Beispiel-Anfrage - WebSocket

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

## Beispiel-Anfrage - JavaScript

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

## JSON-Schema

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
