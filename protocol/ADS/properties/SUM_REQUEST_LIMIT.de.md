# Die PLC-Task ist für jede Anfrage gesperrt. Wenn eine Summen-Anfrage zu viele Anfragen enthält, kann die SPS-Zykluszeit überschritten werden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.Config::SUM_REQUEST_LIMIT"` |
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
            "symbol": "ADS.Config::SUM_REQUEST_LIMIT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::SUM_REQUEST_LIMIT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::SUM_REQUEST_LIMIT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `1` |
| Maximum | `1000` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `500` |

## JSON-Schema

```json
{
    "default": 500,
    "maximum": 1000,
    "minimum": 1,
    "propertyOrder": 8,
    "type": "integer",
    "visibility": "HideInEngineering"
}
```
