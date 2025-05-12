# List all definitions of a particular type.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"GetDefinitions"` |
| Kategorie | symbols |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| type | string |
| resolve | string |

## Beispiel-Anfrage - WebSocket

Get all project definitions.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetDefinitions",
            "writeValue": {
                "resolve": "AddAllRefs",
                "type": "project"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get all project definitions.
```javascript
TcHmi.Server.writeSymbol('GetDefinitions',
    {
        "resolve": "AddAllRefs",
        "type": "project"
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
            'GetDefinitions=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "symbols",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "properties": {
            "resolve": {
                "default": "None",
                "enum": [
                    "AddAllRefs",
                    "Simplify",
                    "None"
                ],
                "type": "string"
            },
            "type": {
                "default": "general",
                "enum": [
                    "server",
                    "framework",
                    "general",
                    "project"
                ],
                "type": "string"
            }
        },
        "type": "object"
    }
}
```
