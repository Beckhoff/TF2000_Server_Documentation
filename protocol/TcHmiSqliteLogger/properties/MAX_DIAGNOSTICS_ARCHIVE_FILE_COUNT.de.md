# Server-Neustart erforderlich.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT"` |
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
            "symbol": "TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Config::MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"integer"` |
| Minimum | `1` |
| Maximum | `16` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `2` |

## JSON-Schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/UINT32"
        },
        {
            "configDescription": "DESC_MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT",
            "default": 2,
            "maximum": 16,
            "minimum": 1,
            "visibility": "HideInEngineering"
        }
    ]
}
```
