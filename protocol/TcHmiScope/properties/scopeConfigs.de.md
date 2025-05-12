# Scope-Konfigurationen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.Config::scopeConfigs"` |
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
            "symbol": "TcHmiScope.Config::scopeConfigs"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiScope.Config::scopeConfigs', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiScope.Config::scopeConfigs=' +
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
        "properties": {
            "AUTOSTART_RECORD": {
                "default": true,
                "type": "boolean"
            },
            "CONFIG_FILE": {
                "format": "base64",
                "type": "string"
            },
            "CONFIG_PATH": {
                "type": "string",
                "visibility": "HideInEngineering"
            },
            "CONFIG_SOURCE": {
                "enum": [
                    "project",
                    "file"
                ],
                "type": "string",
                "visibility": "HideInEngineering"
            }
        },
        "required": [
            "CONFIG_FILE",
            "AUTOSTART_RECORD"
        ],
        "type": "object"
    },
    "configDescription": "DESC_SCOPE_CONFIGS",
    "type": "object"
}
```
