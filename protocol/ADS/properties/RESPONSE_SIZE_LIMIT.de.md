# Die SPS-Task wird für jede Anfrage gesperrt. Ist die Anfrage zu groß, kann die SPS-Zykluszeit überschritten werden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.Config::RESPONSE_SIZE_LIMIT"` |
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
            "symbol": "ADS.Config::RESPONSE_SIZE_LIMIT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::RESPONSE_SIZE_LIMIT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::RESPONSE_SIZE_LIMIT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `2048` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `2097152` |

## JSON-Schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/INT32"
        },
        {
            "default": 2097152,
            "description": "DESC_RESPONSE_SIZE_LIMIT",
            "minimum": 2048,
            "propertyOrder": 7,
            "type": "integer",
            "unit": "byte",
            "visibility": "HideInEngineering"
        }
    ]
}
```
