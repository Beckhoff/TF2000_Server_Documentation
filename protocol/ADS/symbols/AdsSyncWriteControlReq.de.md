# Changes the ADS status and the device status of an ADS server.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.AdsSyncWriteControlReq"` |
| Kategorie | native |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| Runtime | string |
| AdsState | adsState |
| DeviceState | UINT32 |
| WriteData | string |

## Beispiel-Anfrage - WebSocket

Change the ADS status and the device status of the 'PLC1' runtime (use the system service port 10000 to run this sample).
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ADS.AdsSyncWriteControlReq",
            "writeValue": {
                "AdsState": 5,
                "DeviceState": 5,
                "Runtime": "PLC1",
                "WriteData": ""
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Change the ADS status and the device status of the 'PLC1' runtime (use the system service port 10000 to run this sample).
```javascript
TcHmi.Server.writeSymbol('ADS.AdsSyncWriteControlReq',
    {
        "AdsState": 5,
        "DeviceState": 5,
        "Runtime": "PLC1",
        "WriteData": ""
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
            'ADS.AdsSyncWriteControlReq=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "native",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "properties": {
            "AdsState": {
                "$ref": "#/definitions/adsState"
            },
            "DeviceState": {
                "$ref": "tchmi:general#/definitions/UINT32"
            },
            "Runtime": {
                "type": "string"
            },
            "WriteData": {
                "format": "base64",
                "type": "string"
            }
        },
        "required": [
            "Runtime",
            "AdsState",
            "DeviceState",
            "WriteData"
        ],
        "type": "object"
    }
}
```
