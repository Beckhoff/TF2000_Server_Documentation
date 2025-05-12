# Zielsysteme, von denen Daten abgefragt werden können.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiMdp"` |
| Vollständiger Symbol-Pfad | `"TcHmiMdp.Config::targetSystems"` |
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
            "symbol": "TcHmiMdp.Config::targetSystems"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiMdp.Config::targetSystems', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiMdp.Config::targetSystems=' +
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
        "address": "127.0.0.1.1.1"
    }
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "configDescription": "descTargetSystem",
        "properties": {
            "address": {
                "$ref": "tchmi:server#/definitions/adsRoute"
            },
            "enabled": {
                "default": true,
                "type": "boolean"
            },
            "readOnly": {
                "configDescription": "descReadOnly",
                "default": false,
                "type": "boolean"
            }
        },
        "required": [
            "address",
            "enabled",
            "readOnly"
        ],
        "type": "object"
    },
    "configDescription": "descTargetSystems",
    "default": {
        "Local": {
            "address": "127.0.0.1.1.1"
        }
    },
    "defaultConfigurable": true,
    "type": "object"
}
```
