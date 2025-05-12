# Leer lassen, um die Client-Zeitzoneneinstellung zu verwenden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::DEFAULTTIMEZONE"` |
| Sichtbarkeit | AlwaysShow |
| Standardmäßig in jeder Konfiguration enthalten | Nein |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSrv.Config::DEFAULTTIMEZONE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFAULTTIMEZONE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFAULTTIMEZONE=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "allOf": [
        {
            "oneOf": [
                {
                    "$ref": "tchmi:general#/definitions/TimeZone"
                },
                {
                    "default": "client",
                    "enum": [
                        "client"
                    ],
                    "type": "string"
                }
            ]
        },
        {
            "configDescription": "DESC_TIMEZONE"
        }
    ]
}
```
