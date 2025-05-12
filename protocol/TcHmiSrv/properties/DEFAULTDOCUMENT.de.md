# Diese Standardseite wird angezeigt, wenn ein Web-Client eine URL anfordert, die auf eine Verzeichnisstruktur verweist, anstatt auf eine tatsächliche Webseite innerhalb der Verzeichnisstruktur.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::DEFAULTDOCUMENT"` |
| Kategorie | webserver |
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
            "symbol": "TcHmiSrv.Config::DEFAULTDOCUMENT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFAULTDOCUMENT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFAULTDOCUMENT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Duplikate erlaubt | Ja |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
[
    "Default.html"
]
```

## JSON-Schema

```json
{
    "category": "webserver",
    "default": [
        "Default.html"
    ],
    "items": {
        "format": "filename",
        "type": "string"
    },
    "type": "array",
    "uniqueItems": true
}
```
