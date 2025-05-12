# Der gängigste Mechanismus ist 'Simple'. 'Digest-MD5' wird empfohlen, wenn TLS nicht verfügbar ist.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::AUTHENTICATION_MECHANISM"` |
| Kategorie | authentication |
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
            "symbol": "TcHmiLdap.Config::AUTHENTICATION_MECHANISM"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::AUTHENTICATION_MECHANISM', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::AUTHENTICATION_MECHANISM=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"Simple"` |

## Wert des Aufzählungstyps

- `"Simple"`
- `"Digest-MD5"`

## JSON-Schema

```json
{
    "category": "authentication",
    "default": "Simple",
    "enum": [
        "Simple",
        "Digest-MD5"
    ],
    "propertyOrder": 6,
    "type": "string"
}
```
