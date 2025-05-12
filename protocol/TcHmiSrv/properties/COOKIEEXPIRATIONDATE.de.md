# Der Server verwendet Cookies, um Sitzungs-IDs zu speichern. Achten Sie darauf, dass das Cookie-Ablaufdatum und die Zeit der automatischen Abmeldung nicht im Widerspruch zueinander stehen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::COOKIEEXPIRATIONDATE"` |
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
            "symbol": "TcHmiSrv.Config::COOKIEEXPIRATIONDATE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::COOKIEEXPIRATIONDATE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::COOKIEEXPIRATIONDATE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | timespan |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"P30D"` |

## JSON-Schema

```json
{
    "category": "webserver",
    "default": "P30D",
    "format": "timespan",
    "type": "string"
}
```
