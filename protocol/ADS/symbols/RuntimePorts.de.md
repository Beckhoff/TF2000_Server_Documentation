# List the runtime ports of a specific TwinCAT system.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.RuntimePorts"` |
| Kategorie | wrapperFunctions |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

List the runtime ports of the local TwinCAT system.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ADS.RuntimePorts",
            "writeValue": {
                "NETID": "127.0.0.1.1.1"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

List the runtime ports of the local TwinCAT system.
```javascript
TcHmi.Server.writeSymbol('ADS.RuntimePorts',
    {
        "NETID": "127.0.0.1.1.1"
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
            'ADS.RuntimePorts=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "wrapperFunctions",
    "readValue": {
        "function": true,
        "items": {
            "properties": {
                "label": {
                    "type": "string"
                },
                "name": {
                    "type": "string"
                },
                "value": {
                    "type": "integer"
                }
            },
            "required": [
                "label",
                "value"
            ],
            "type": "object"
        },
        "type": "array"
    },
    "writeValue": {
        "anyOf": [
            {
                "properties": {
                    "NETID": {
                        "format": "amsnetid",
                        "type": "string"
                    },
                    "all": {
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
