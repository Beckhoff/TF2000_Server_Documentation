# Liste mit allen historisierten Symbolen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteHistorize.Config::historizedSymbolList"` |
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
            "symbol": "TcHmiSqliteHistorize.Config::historizedSymbolList"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteHistorize.Config::historizedSymbolList', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteHistorize.Config::historizedSymbolList=' +
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
            "interval": {
                "default": "PT1S",
                "format": "timespan",
                "formatMinimum": "PT0.01S",
                "type": "string"
            },
            "maxEntries": {
                "default": 10000,
                "minimum": 1,
                "type": "integer"
            },
            "recordingEnabled": {
                "default": true,
                "type": "boolean"
            },
            "rowLimit": {
                "default": 100000,
                "minimum": 1,
                "type": "integer",
                "visibility": "HideInEngineering"
            },
            "version": {
                "default": 1.0,
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
            "rowLimit"
        ],
        "title": "TITLE_HISTORIZE_SYMBOL",
        "type": "object"
    },
    "configDescription": "descHistorizedSymbolList",
    "defaultConfigurable": true,
    "propertyOrder": 1,
    "type": "object"
}
```
