# List containing all historized symbols.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Full symbol path | `"TcHmiPostgresHistorize.Config::historizedSymbolList"` |
| Visibility | AlwaysShow |
| Contained in every configuration by default | Yes |

## Sample request - WebSocket

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

## Sample request - JavaScript

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
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

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
