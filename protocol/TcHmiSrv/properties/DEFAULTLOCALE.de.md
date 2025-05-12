# Leer lassen, um die Client-Spracheinstellung zu verwenden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::DEFAULTLOCALE"` |
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
            "symbol": "TcHmiSrv.Config::DEFAULTLOCALE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFAULTLOCALE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFAULTLOCALE=' +
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
                    "$ref": "tchmi:general#/definitions/Locale"
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
            "configDescription": "DESC_LOCALE"
        }
    ]
}
```
