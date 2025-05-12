# Wenn dieser Wert erreicht wird, werden die Ereignisse auf mehreren Seiten angezeigt

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLua"` |
| Vollständiger Symbol-Pfad | `"TcHmiLua.Config::LOG_PAGE_MAX_ENTRIES"` |
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
            "symbol": "TcHmiLua.Config::LOG_PAGE_MAX_ENTRIES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLua.Config::LOG_PAGE_MAX_ENTRIES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLua.Config::LOG_PAGE_MAX_ENTRIES=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `10` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `200` |

## JSON-Schema

```json
{
    "configDescription": "DESC_LOG_PAGE_MAX_ENTRIES",
    "default": 200,
    "minimum": 10,
    "type": "integer"
}
```
