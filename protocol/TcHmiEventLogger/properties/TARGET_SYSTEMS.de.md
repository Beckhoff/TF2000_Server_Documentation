# Zielsysteme, von denen Ereignisse und Alarme abgefragt werden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiEventLogger.Config::TARGET_SYSTEMS"` |
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
            "symbol": "TcHmiEventLogger.Config::TARGET_SYSTEMS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEventLogger.Config::TARGET_SYSTEMS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEventLogger.Config::TARGET_SYSTEMS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
{
    "Local": {
        "ADDRESS": "127.0.0.1.1.1",
        "ENABLED": true
    }
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "configDescription": "DESC_TARGET_SYSTEM",
        "properties": {
            "ADDRESS": {
                "allOf": [
                    {
                        "$ref": "tchmi:server#/definitions/adsRoute"
                    },
                    {
                        "configDescription": "DESC_ADS_ROUTE"
                    }
                ]
            },
            "ENABLED": {
                "default": true,
                "type": "boolean"
            }
        },
        "required": [
            "ADDRESS",
            "ENABLED"
        ],
        "type": "object"
    },
    "configDescription": "DESC_TARGET_SYSTEMS",
    "default": {
        "Local": {
            "ADDRESS": "127.0.0.1.1.1",
            "ENABLED": true
        }
    },
    "defaultConfigurable": true,
    "type": "object"
}
```
