# Writes data synchronously to an ADS device.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.AdsSyncWriteReq"` |
| Kategorie | native |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| Runtime | string |
| IndexGroup | UINT32 |
| IndexOffset | UINT32 |
| WriteData | string |

## Beispiel-Anfrage - WebSocket

Release an ADS variable handle of the 'PLC1' runtime.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ADS.AdsSyncWriteReq",
            "writeValue": {
                "IndexGroup": 61446,
                "IndexOffset": 0,
                "Runtime": "PLC1",
                "WriteData": "AAAAAA=="
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Release an ADS variable handle of the 'PLC1' runtime.
```javascript
TcHmi.Server.writeSymbol('ADS.AdsSyncWriteReq',
    {
        "IndexGroup": 61446,
        "IndexOffset": 0,
        "Runtime": "PLC1",
        "WriteData": "AAAAAA=="
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
            'ADS.AdsSyncWriteReq=' +
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
            "IndexGroup": {
                "$ref": "tchmi:general#/definitions/UINT32"
            },
            "IndexOffset": {
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
            "IndexGroup",
            "IndexOffset",
            "WriteData"
        ],
        "type": "object"
    }
}
```
