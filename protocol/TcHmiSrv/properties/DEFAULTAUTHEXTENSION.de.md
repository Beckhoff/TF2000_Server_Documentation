# Es können mehrere Authentifizierungserweiterungen gleichzeitig verwendet werden. Die Standard-Authentifizierungserweiterung wird standardmäßig auf der Login-Seite ausgewählt.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::DEFAULTAUTHEXTENSION"` |
| Kategorie | security |
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
            "symbol": "TcHmiSrv.Config::DEFAULTAUTHEXTENSION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFAULTAUTHEXTENSION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFAULTAUTHEXTENSION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"TcHmiUserManagement"` |

## JSON-Schema

```json
{
    "category": "security",
    "default": "TcHmiUserManagement",
    "optionMethod": {
        "filter": [
            {
                "comparator": "==",
                "path": "authExtension",
                "value": true
            }
        ],
        "symbol": "ListDomains"
    },
    "type": "string"
}
```
