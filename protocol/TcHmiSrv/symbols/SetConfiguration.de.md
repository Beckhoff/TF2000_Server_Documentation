# Set configuration.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"SetConfiguration"` |
| Kategorie | configurationsAndFilesystem |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| name | string |
| symbol | string |
| domain | string |
| data |  |

## Beispiel-Anfrage - WebSocket

Change the default authentication extension in the 'default' configuration.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "SetConfiguration",
            "writeValue": {
                "data": "TcHmiLdap",
                "domain": "TcHmiSrv",
                "name": "default",
                "symbol": "DEFAULTAUTHEXTENSION"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Change the default authentication extension in the 'default' configuration.
```javascript
TcHmi.Server.writeSymbol('SetConfiguration',
    {
        "data": "TcHmiLdap",
        "domain": "TcHmiSrv",
        "name": "default",
        "symbol": "DEFAULTAUTHEXTENSION"
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
            'SetConfiguration=' +
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
            "data": {},
            "domain": {
                "type": "string"
            },
            "name": {
                "type": "string"
            },
            "symbol": {
                "default": "",
                "type": "string"
            }
        },
        "required": [
            "name",
            "domain",
            "data"
        ],
        "type": "object"
    }
}
```
