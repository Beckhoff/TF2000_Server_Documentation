# Kürzere Gültigkeitsdauern begrenzen den Schaden durch Schlüsselkompromittierung und Falschausstellungen. Gestohlene Schlüssel und falsch ausgestellte Zertifikate sind für einen kürzeren Zeitraum gültig.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::CERTIFICATEEXPIRATION"` |
| Kategorie | security |
| Sichtbarkeit | HideInEngineering |
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
            "symbol": "TcHmiSrv.Config::CERTIFICATEEXPIRATION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::CERTIFICATEEXPIRATION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::CERTIFICATEEXPIRATION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | timespan |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"P14000D"` |

## JSON-Schema

```json
{
    "category": "security",
    "default": "P14000D",
    "defaultConfigurable": true,
    "format": "timespan",
    "type": "string",
    "visibility": "HideInEngineering"
}
```
