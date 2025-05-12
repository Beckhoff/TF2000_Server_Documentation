# Die GZIP-Komprimierung wird vom Server und den Web-Clients verwendet, um die Übertragungsgeschwindigkeit und die Bandbreitennutzung zu verbessern.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::DEFLATECOMPRESSIONLEVEL"` |
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
            "symbol": "TcHmiSrv.Config::DEFLATECOMPRESSIONLEVEL"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFLATECOMPRESSIONLEVEL', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFLATECOMPRESSIONLEVEL=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Minimum | `0` |
| Maximum | `9` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `5` |

## Optionen

| Wert | Label |
| ---- | ----- |
| `1` | Beste Geschwindigkeit |
| `5` | Medium |
| `9` | Beste Größe |

## JSON-Schema

```json
{
    "category": "webserver",
    "default": 5,
    "maximum": 9,
    "minimum": 0,
    "options": [
        {
            "label": "GZIP_BEST_SPEED",
            "value": 1
        },
        {
            "label": "GZIP_MEDIUM",
            "value": 5
        },
        {
            "label": "GZIP_BEST_SIZE",
            "value": 9
        }
    ],
    "type": "integer"
}
```
