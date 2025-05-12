# Reads the identification and version number of an ADS server.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.AdsSyncReadDeviceInfoReq"` |
| Kategorie | native |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Read the identification and version number of the 'PLC1' runtime.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ADS.AdsSyncReadDeviceInfoReq",
            "writeValue": "PLC1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Read the identification and version number of the 'PLC1' runtime.
```javascript
TcHmi.Server.writeSymbol('ADS.AdsSyncReadDeviceInfoReq',
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
            'ADS.AdsSyncReadDeviceInfoReq=' +
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
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "description": "Ads runtime.",
        "type": "string"
    }
}
```
