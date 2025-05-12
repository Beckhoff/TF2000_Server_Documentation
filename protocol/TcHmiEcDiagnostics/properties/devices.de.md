# EtherCAT-Geräte

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.Config::devices"` |
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
            "symbol": "TcHmiEcDiagnostics.Config::devices"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEcDiagnostics.Config::devices', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEcDiagnostics.Config::devices=' +
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
    "Device1": {
        "enabled": true,
        "masterNetId": "0.0.0.0.2.1",
        "targetNetId": "0.0.0.0.1.1"
    }
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "properties": {
            "enabled": {
                "default": true,
                "type": "boolean"
            },
            "masterNetId": {
                "format": "amsnetid",
                "optionMethod": {
                    "symbol": "{domain}.ListMastersOfRoute",
                    "writeValue": {
                        "$data": "#/properties/devices/additionalProperties/targetNetId"
                    }
                },
                "type": "string"
            },
            "targetNetId": {
                "format": "amsnetid",
                "optionMethod": {
                    "symbol": "ADS.ListRoutes"
                },
                "type": "string"
            }
        },
        "required": [
            "enabled",
            "targetNetId",
            "masterNetId"
        ],
        "type": "object"
    },
    "default": {
        "Device1": {
            "enabled": true,
            "masterNetId": "0.0.0.0.2.1",
            "targetNetId": "0.0.0.0.1.1"
        }
    },
    "defaultConfigurable": true,
    "type": "object"
}
```
