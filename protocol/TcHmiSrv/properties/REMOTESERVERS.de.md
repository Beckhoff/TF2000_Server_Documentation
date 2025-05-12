# Verbindungen zu anderen HMI-Servern. Die Symbol-Mappings von Remote-Servern können wie Symbole von Erweiterungen des aktuellen Servers verwendet werden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::REMOTESERVERS"` |
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
            "symbol": "TcHmiSrv.Config::REMOTESERVERS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::REMOTESERVERS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::REMOTESERVERS=' +
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
        "properties": {
            "REMOTE_CONNECT_TIMEOUT": {
                "default": "PT5S",
                "format": "timespan",
                "type": "string"
            },
            "REMOTE_ENABLED": {
                "default": true,
                "type": "boolean"
            },
            "REMOTE_PASSWORD": {
                "default": "",
                "format": "masked",
                "propertyOrder": 3,
                "type": "string"
            },
            "REMOTE_URL": {
                "propertyOrder": 1,
                "type": "string"
            },
            "REMOTE_USERNAME": {
                "configDescription": "DESC_REMOTE_USERNAME",
                "default": "",
                "propertyOrder": 2,
                "type": "string"
            }
        },
        "required": [
            "REMOTE_ENABLED",
            "REMOTE_URL",
            "REMOTE_USERNAME",
            "REMOTE_PASSWORD",
            "REMOTE_CONNECT_TIMEOUT"
        ],
        "title": "REMOTESERVERS_TITLE",
        "type": "object"
    },
    "configDescription": "DESC_REMOTESERVERS",
    "type": "object"
}
```
