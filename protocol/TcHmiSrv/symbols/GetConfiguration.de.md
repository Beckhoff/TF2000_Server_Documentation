# Get a specific configuration. Requires access to the '*.Config' symbol of the requested domain.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"GetConfiguration"` |
| Kategorie | configurationsAndFilesystem |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| name | string |
| domain | string |
| full | boolean |

## Beispiel-Anfrage - WebSocket

Get the ADS extension configuration for CX9000.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetConfiguration",
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

## Beispiel-Anfrage - JavaScript

Get the ADS extension configuration for CX9000.
```javascript
TcHmi.Server.writeSymbol('GetConfiguration',
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
            'GetConfiguration=' +
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
