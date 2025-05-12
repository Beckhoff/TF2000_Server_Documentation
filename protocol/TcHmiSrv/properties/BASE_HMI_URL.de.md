# Diese URL wird auf der Konfigurationsseite verlinkt

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::BASE_HMI_URL"` |
| Kategorie | advanced |
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
            "symbol": "TcHmiSrv.Config::BASE_HMI_URL"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::BASE_HMI_URL', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::BASE_HMI_URL=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `""` |

## JSON-Schema

```json
{
    "category": "advanced",
    "configDescription": "DESC_BASE_HMI_URL",
    "default": "",
    "defaultConfigurable": true,
    "type": "string"
}
```
