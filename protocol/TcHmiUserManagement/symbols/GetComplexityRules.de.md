# Get a list of all enabled password complexity rules. All regular expressions use the ECMAScript syntax.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.GetComplexityRules"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.GetComplexityRules"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiUserManagement.GetComplexityRules', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiUserManagement.GetComplexityRules=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "additionalProperties": {
            "properties": {
                "localizationParameters": {
                    "additionalProperties": {
                        "type": "string"
                    },
                    "type": "object"
                },
                "regex": {
                    "format": "regex",
                    "type": "string"
                }
            },
            "required": [
                "regex"
            ],
            "type": "object"
        },
        "function": true,
        "type": "object"
    }
}
```
