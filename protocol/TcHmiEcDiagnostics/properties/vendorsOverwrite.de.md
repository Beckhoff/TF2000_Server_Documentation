# Hersteller-ID hinzufügen

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.Config::vendorsOverwrite"` |
| Sichtbarkeit | AlwaysShow |
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
            "symbol": "TcHmiEcDiagnostics.Config::vendorsOverwrite"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEcDiagnostics.Config::vendorsOverwrite', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEcDiagnostics.Config::vendorsOverwrite=' +
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
    "1": {
        "longName": "EtherCAT Technology Group",
        "shortName": "ETG"
    },
    "2": {
        "longName": "Beckhoff Automation GmbH & Co. KG",
        "shortName": "Beckhoff"
    }
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "properties": {
            "devices": {
                "items": {
                    "additionalProperties": false,
                    "properties": {
                        "longName": {
                            "type": "string"
                        },
                        "pattern": {
                            "type": "string"
                        },
                        "shortName": {
                            "type": "string"
                        }
                    },
                    "required": [
                        "pattern"
                    ],
                    "type": "object"
                },
                "type": "array"
            },
            "longName": {
                "type": "string"
            },
            "shortName": {
                "type": "string"
            }
        },
        "required": [
            "devices"
        ],
        "type": "object"
    },
    "default": {
        "1": {
            "longName": "EtherCAT Technology Group",
            "shortName": "ETG"
        },
        "2": {
            "longName": "Beckhoff Automation GmbH & Co. KG",
            "shortName": "Beckhoff"
        }
    },
    "type": "object"
}
```
