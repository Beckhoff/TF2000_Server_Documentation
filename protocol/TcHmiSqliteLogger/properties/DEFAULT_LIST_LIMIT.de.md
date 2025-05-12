# Dieses Limit wird für alle Anfragen verwendet, für die kein anderes Limit angegeben wurde.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteLogger.Config::DEFAULT_LIST_LIMIT"` |
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
            "symbol": "TcHmiSqliteLogger.Config::DEFAULT_LIST_LIMIT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Config::DEFAULT_LIST_LIMIT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Config::DEFAULT_LIST_LIMIT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `1` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `1000` |

## JSON-Schema

```json
{
    "configDescription": "DESC_DEFAULT_LIST_LIMIT",
    "default": 1000,
    "minimum": 1,
    "type": "integer"
}
```
