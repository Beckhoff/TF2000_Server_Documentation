# Aktive Alarme werden immer importiert, auch wenn dadurch dieses Limit überschritten wird.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiAlarm"` |
| Vollständiger Symbol-Pfad | `"TcHmiAlarm.Config::limitEventCount"` |
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
            "symbol": "TcHmiAlarm.Config::limitEventCount"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiAlarm.Config::limitEventCount', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiAlarm.Config::limitEventCount=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `1` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `1000` |

## JSON-Schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/UINT32"
        },
        {
            "configDescription": "DESC_LIMIT_EVENT_COUNT",
            "default": 1000,
            "minimum": 1,
            "propertyOrder": 1,
            "type": "integer"
        }
    ]
}
```
