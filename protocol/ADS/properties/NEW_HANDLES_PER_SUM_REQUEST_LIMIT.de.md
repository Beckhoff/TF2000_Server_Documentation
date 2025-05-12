# TwinCATs Handle-Buffer wird nicht während einer Summen-Anfrage vergrößert. Das Anlegen von zu vielen ADS-Handles in einer einzigen Summen-Anfrage führt zu Fehlern, wenn TwinCATs Handle-Buffer voll ist.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.Config::NEW_HANDLES_PER_SUM_REQUEST_LIMIT"` |
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
            "symbol": "ADS.Config::NEW_HANDLES_PER_SUM_REQUEST_LIMIT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::NEW_HANDLES_PER_SUM_REQUEST_LIMIT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::NEW_HANDLES_PER_SUM_REQUEST_LIMIT=' +
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
| Default-Wert | `100` |

## JSON-Schema

```json
{
    "default": 100,
    "maximum": 1000,
    "minimum": 1,
    "propertyOrder": 9,
    "type": "integer",
    "visibility": "HideInEngineering"
}
```
