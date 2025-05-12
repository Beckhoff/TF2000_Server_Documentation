# Definiert, wie lange Server-Antworten zwischengespeichert werden dürfen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::CLIENT_CACHE_MAX_AGE"` |
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
            "symbol": "TcHmiSrv.Config::CLIENT_CACHE_MAX_AGE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::CLIENT_CACHE_MAX_AGE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::CLIENT_CACHE_MAX_AGE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `0` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `0` |

## JSON-Schema

```json
{
    "category": "webserver",
    "configDescription": "DESC_CLIENT_CACHE_MAX_AGE",
    "default": 0,
    "minimum": 0,
    "type": "integer",
    "unit": "seconds"
}
```
