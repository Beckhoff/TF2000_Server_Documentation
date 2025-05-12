# Eine Liste von Passwörtern, welche Benutzer nicht wählen können. Ein Passwort pro Zeile.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.Config::PASSWORD_BLACKLIST"` |
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
            "symbol": "TcHmiUserManagement.Config::PASSWORD_BLACKLIST"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiUserManagement.Config::PASSWORD_BLACKLIST', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiUserManagement.Config::PASSWORD_BLACKLIST=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | multiline |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `""` |

## JSON-Schema

```json
{
    "default": "",
    "format": "multiline",
    "type": "string"
}
```
