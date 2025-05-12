# Es werden IPv4- und IPv6-Endpunkte unterstützt. Nur HTTPS-Endpunkte sollten für den Remote-Zugriff aktiviert werden. Verwenden Sie die Wildcard-Adressen '0.0.0.0' und '[::]', um Remote-Verbindungen auf allen Netzwerkschnittstellen zu akzeptieren.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::ENDPOINTS"` |
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
            "symbol": "TcHmiSrv.Config::ENDPOINTS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::ENDPOINTS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::ENDPOINTS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Duplikate erlaubt | Ja |
| Minimale Anzahl von Elementen | 1 |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
[
    "http://127.0.0.1:2010",
    "https://[::]:2020"
]
```

## JSON-Schema

```json
{
    "category": "webserver",
    "default": [
        "http://127.0.0.1:2010",
        "https://[::]:2020"
    ],
    "items": {
        "type": "string"
    },
    "minItems": 1,
    "type": "array",
    "uniqueItems": true
}
```
