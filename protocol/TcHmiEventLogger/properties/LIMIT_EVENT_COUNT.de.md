# Aktive Alarme werden immer importiert, auch wenn dadurch dieses Limit überschritten wird.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEventLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiEventLogger.Config::LIMIT_EVENT_COUNT"` |
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
            "symbol": "TcHmiEventLogger.Config::LIMIT_EVENT_COUNT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEventLogger.Config::LIMIT_EVENT_COUNT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEventLogger.Config::LIMIT_EVENT_COUNT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `0` |
| Maximum | `4294967295` |
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
            "default": 1000
        }
    ]
}
```
