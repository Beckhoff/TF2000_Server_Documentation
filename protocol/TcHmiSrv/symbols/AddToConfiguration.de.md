# Add variable to configuration

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"AddToConfiguration"` |
| Kategorie | configurationsAndFilesystem |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| name | string | Name of the configuration. |
| domain | string | Domain of the config value. |
| path | string | Path of the config value. |

## Beispiel-Anfrage - WebSocket

Add custom file setting to CX9000 configuration
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "AddToConfiguration",
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

## Beispiel-Anfrage - JavaScript

Add custom file setting to CX9000 configuration
```javascript
TcHmi.Server.writeSymbol('AddToConfiguration',
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
            'AddToConfiguration=' +
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
