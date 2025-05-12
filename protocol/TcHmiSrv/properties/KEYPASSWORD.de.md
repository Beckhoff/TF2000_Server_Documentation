# Passwort für die Dekodierung des privaten Schlüssels oder der PFX-Datei. Wenn das Zertifikat kein Passwort benötigt, kann dieses Feld leer bleiben.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::KEYPASSWORD"` |
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
            "symbol": "TcHmiSrv.Config::KEYPASSWORD"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::KEYPASSWORD', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::KEYPASSWORD=' +
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
    "propertyOrder": 10,
    "type": "string"
}
```
