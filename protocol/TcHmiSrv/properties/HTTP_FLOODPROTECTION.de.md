# Erlaubte HTTP-Anfragen pro Client IP pro Sekunde pro URI

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::HTTP_FLOODPROTECTION"` |
| Kategorie | advanced |
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
            "symbol": "TcHmiSrv.Config::HTTP_FLOODPROTECTION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::HTTP_FLOODPROTECTION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::HTTP_FLOODPROTECTION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `0` |
| Maximum | `4294967295` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `100` |

## JSON-Schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/UINT32"
        },
        {
            "category": "advanced",
            "configDescription": "DESC_HTTP_FLOODPROTECTION",
            "default": 100
        }
    ]
}
```
