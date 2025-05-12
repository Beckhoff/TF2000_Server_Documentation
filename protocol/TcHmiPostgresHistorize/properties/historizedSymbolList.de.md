# Liste mit allen historisierten Symbolen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiPostgresHistorize.Config::historizedSymbolList"` |
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
            "symbol": "TcHmiPostgresHistorize.Config::historizedSymbolList"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiPostgresHistorize.Config::historizedSymbolList', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiPostgresHistorize.Config::historizedSymbolList=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "configDescription": "descHistorizedSymbol",
        "keyOptionMethod": {
            "symbol": "ListSymbolNames"
        },
        "properties": {
            "deletionInterval": {
                "configDescription": "descDeletionInterval",
                "default": "PT1M",
                "format": "timespan",
                "formatMinimum": "PT1S",
                "type": "string"
            },
            "interval": {
                "default": "PT1S",
                "format": "timespan",
                "formatMinimum": "PT0.01S",
                "type": "string"
            },
            "maxEntries": {
                "default": 10000,
                "type": "integer"
            },
            "recordingEnabled": {
                "default": true,
                "type": "boolean"
            },
            "version": {
                "optionMethod": {
                    "orderBy": "DESC",
                    "symbol": "GetSchema::{key}",
                    "writeValue": {
                        "resolve": "AllVersions",
                        "symbol": {
                            "$data": "#/properties/historizedSymbolList/additionalProperties"
                        }
                    }
                },
                "optionMethodAllowCustom": false,
                "type": "number"
            }
        },
        "required": [
            "maxEntries",
            "interval",
            "recordingEnabled",
            "deletionInterval"
        ],
        "title": "historizeSymbol",
        "type": "object"
    },
    "configDescription": "descHistorizedSymbolList",
    "defaultConfigurable": true,
    "propertyOrder": 1,
    "type": "object"
}
```
