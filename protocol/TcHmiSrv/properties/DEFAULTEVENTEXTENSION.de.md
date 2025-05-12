# Wenn das Funktionssymbol 'ListEvents' aufgerufen wird, werden die Ereignisse von der Standard-Ereigniserweiterung angefordert.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::DEFAULTEVENTEXTENSION"` |
| Kategorie | advanced |
| Sichtbarkeit | HideInEngineering |
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
            "symbol": "TcHmiSrv.Config::DEFAULTEVENTEXTENSION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFAULTEVENTEXTENSION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFAULTEVENTEXTENSION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"TcHmiSqliteLogger"` |

## JSON-Schema

```json
{
    "category": "advanced",
    "default": "TcHmiSqliteLogger",
    "type": "string",
    "visibility": "HideInEngineering"
}
```
