# Writes data synchronously into an ADS server and receives data back from the ADS device.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.AdsSyncReadWriteReq"` |
| Kategorie | native |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| Runtime | string |
| IndexGroup | UINT32 |
| IndexOffset | UINT32 |
| ReadLen | UINT32 |
| WriteData | string |

## Beispiel-Anfrage - WebSocket

Get information about the 'TwinCAT_SystemInfoVarList._Appinfo.OnlineChangeCnt' ADS symbol of runtime 'PLC1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ADS.AdsSyncReadWriteReq",
            "writeValue": {
                "IndexGroup": 61449,
                "IndexOffset": 0,
                "ReadLen": 255,
                "Runtime": "PLC1",
                "WriteData": "VHdpbkNBVF9TeXN0ZW1JbmZvVmFyTGlzdC5fQXBwaW5mby5PbmxpbmVDaGFuZ2VDbnQ="
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get information about the 'TwinCAT_SystemInfoVarList._Appinfo.OnlineChangeCnt' ADS symbol of runtime 'PLC1'.
```javascript
TcHmi.Server.writeSymbol('ADS.AdsSyncReadWriteReq',
    {
        "IndexGroup": 61449,
        "IndexOffset": 0,
        "ReadLen": 255,
        "Runtime": "PLC1",
        "WriteData": "VHdpbkNBVF9TeXN0ZW1JbmZvVmFyTGlzdC5fQXBwaW5mby5PbmxpbmVDaGFuZ2VDbnQ="
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
            'ADS.AdsSyncReadWriteReq=' +
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
            "ReadLen": {
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
            "ReadLen",
            "WriteData"
        ],
        "type": "object"
    }
}
```
