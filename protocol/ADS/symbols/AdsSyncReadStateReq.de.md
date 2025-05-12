# Reads the ADS status and the device status of an ADS server.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.AdsSyncReadStateReq"` |
| Kategorie | native |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Read the ADS status and the device status of the 'PLC1' runtime.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ADS.AdsSyncReadStateReq",
            "writeValue": "PLC1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Read the ADS status and the device status of the 'PLC1' runtime.
```javascript
TcHmi.Server.writeSymbol('ADS.AdsSyncReadStateReq',
    "PLC1",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'ADS.AdsSyncReadStateReq=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "native",
    "readValue": {
        "function": true,
        "properties": {
            "AdsState": {
                "$ref": "#/definitions/adsState"
            },
            "DeviceState": {
                "type": "integer"
            }
        },
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "oneOf": [
            {
                "description": "Ads runtime.",
                "type": "string"
            },
            {
                "properties": {
                    "Port": {
                        "allOf": [
                            {
                                "$ref": "tchmi:general#/definitions/UINT32"
                            },
                            {
                                "const": 10000,
                                "description": "Execute the request for a different ADS port"
                            }
                        ]
                    },
                    "Runtime": {
                        "description": "Ads runtime.",
                        "type": "string"
                    }
                },
                "required": [
                    "Runtime"
                ],
                "type": "object"
            }
        ]
    }
}
```
