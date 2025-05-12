# Anfragen mit HTTP-Headern, die größer sind als diese Grenze, werden vom Web-Server abgelehnt.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::MAXHTTPHEADERSIZE"` |
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
            "symbol": "TcHmiSrv.Config::MAXHTTPHEADERSIZE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::MAXHTTPHEADERSIZE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::MAXHTTPHEADERSIZE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `1024` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `32768` |

## JSON-Schema

```json
{
    "category": "advanced",
    "default": 32768,
    "minimum": 1024,
    "type": "integer",
    "unit": "byte"
}
```
