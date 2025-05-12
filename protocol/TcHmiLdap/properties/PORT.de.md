# Die gängigsten Ports sind 636 für TLS und 389 für unverschlüsselte Verbindungen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::PORT"` |
| Sichtbarkeit | AlwaysShow |
| Standardmäßig in jeder Konfiguration enthalten | Ja |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiLdap.Config::PORT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::PORT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::PORT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `1` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `389` |

## JSON-Schema

```json
{
    "default": 389,
    "defaultConfigurable": true,
    "minimum": 1,
    "propertyOrder": 2,
    "type": "integer"
}
```
