# Die Zeit zwischen dem Schreiben jeder Transaktion in die Datenbank.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteHistorize.Config::commitInterval"` |
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
            "symbol": "TcHmiSqliteHistorize.Config::commitInterval"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteHistorize.Config::commitInterval', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteHistorize.Config::commitInterval=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | timespan |
| Minimum | `PT1S` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"PT10S"` |

## JSON-Schema

```json
{
    "configDescription": "descCommitInterval",
    "default": "PT10S",
    "format": "timespan",
    "formatMinimum": "PT1S",
    "propertyOrder": 6,
    "type": "string",
    "visibility": "HideInEngineering"
}
```
