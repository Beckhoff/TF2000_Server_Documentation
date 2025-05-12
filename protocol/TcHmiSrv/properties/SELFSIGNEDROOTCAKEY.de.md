# Dieser Schlüssel wird zur Entschlüsselung des Root-Zertifikats verwendet.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::SELFSIGNEDROOTCAKEY"` |
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
            "symbol": "TcHmiSrv.Config::SELFSIGNEDROOTCAKEY"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::SELFSIGNEDROOTCAKEY', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::SELFSIGNEDROOTCAKEY=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | base64 |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `""` |

## JSON-Schema

```json
{
    "category": "security",
    "default": "",
    "format": "base64",
    "propertyOrder": 8,
    "type": "string"
}
```
