# Server-Neustart erforderlich.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE"` |
| Sichtbarkeit | HideInEngineering |
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
            "symbol": "TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `10000` |
| Maximum | `4294967295` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `52428800` |

## JSON-Schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/UINT32"
        },
        {
            "configDescription": "DESC_MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE",
            "default": 52428800,
            "minimum": 10000,
            "unit": "byte",
            "visibility": "HideInEngineering"
        }
    ]
}
```
