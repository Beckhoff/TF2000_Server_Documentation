# Get information about a specific license by sending a request to the TwinCAT license server.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.CheckLicense"` |
| Kategorie | wrapperFunctions |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Check the TC3 HMI Clients license.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ADS.CheckLicense",
            "writeValue": "37E5160D-987B-4640-888D-0F97727B53E2"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Check the TC3 HMI Clients license.
```javascript
TcHmi.Server.writeSymbol('ADS.CheckLicense',
    "37E5160D-987B-4640-888D-0F97727B53E2",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'ADS.CheckLicense=' +
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
        "properties": {
            "count": {
                "$ref": "tchmi:general#/definitions/UINT32"
            },
            "expireTimeUTC": {
                "format": "date-time",
                "type": "string"
            },
            "result": {
                "$ref": "tchmi:general#/definitions/UINT32"
            }
        },
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
