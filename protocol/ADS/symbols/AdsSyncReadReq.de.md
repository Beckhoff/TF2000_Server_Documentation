# Reads data synchronously from an ADS server.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.AdsSyncReadReq"` |
| Kategorie | native |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| Runtime | string |
| IndexGroup | UINT32 |
| IndexOffset | UINT32 |
| ReadLen | UINT32 |

## Beispiel-Anfrage - WebSocket

Enumerate the first ADS route of the configured runtime (use the system service port 10000 to run this sample).
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ADS.AdsSyncReadReq",
            "writeValue": {
                "IndexGroup": 803,
                "IndexOffset": 0,
                "ReadLen": 1536,
                "Runtime": "PLC1"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Enumerate the first ADS route of the configured runtime (use the system service port 10000 to run this sample).
```javascript
TcHmi.Server.writeSymbol('ADS.AdsSyncReadReq',
    {
        "IndexGroup": 803,
        "IndexOffset": 0,
        "ReadLen": 1536,
        "Runtime": "PLC1"
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
            'ADS.AdsSyncReadReq=' +
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
            }
        },
        "required": [
            "Runtime",
            "IndexGroup",
            "ReadLen"
        ],
        "type": "object"
    }
}
```
