# Diese Header werden in allen HTTP-Antworten gesetzt.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::GLOBALHTTPHEADERS"` |
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
            "symbol": "TcHmiSrv.Config::GLOBALHTTPHEADERS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::GLOBALHTTPHEADERS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::GLOBALHTTPHEADERS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | multiline |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```txt
{LASTMODIFIED}
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type-Options: nosniff
```

## JSON-Schema

```json
{
    "category": "webserver",
    "configDescription": "DESC_GLOBAL_HTTP_HEADERS",
    "default": "{LASTMODIFIED}\nStrict-Transport-Security: max-age=31536000; includeSubDomains\nX-Content-Type-Options: nosniff",
    "format": "multiline",
    "type": "string"
}
```
