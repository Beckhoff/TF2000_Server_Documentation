# Synchronisation aus ist schneller, kann aber im Fall eines Stromausfalls die Datenbank korrumpieren.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteLogger"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteLogger.Config::MODE"` |
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
            "symbol": "TcHmiSqliteLogger.Config::MODE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteLogger.Config::MODE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteLogger.Config::MODE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `1` |

## Optionen

| Wert | Label |
| ---- | ----- |
| `0` | Synchronisation extra |
| `1` | Synchronisation vollständig |
| `3` | Synchronisation normal |
| `4` | Synchronisation aus |

## JSON-Schema

```json
{
    "configDescription": "DESC_MODE",
    "default": 1,
    "enum": [
        0,
        1,
        3,
        4
    ],
    "options": [
        {
            "label": "ENUM_SYNCHRONOUS_EXTRA_PERSIST",
            "value": 0
        },
        {
            "label": "ENUM_SYNCHRONOUS_FULL_PERSIST",
            "value": 1
        },
        {
            "label": "ENUM_SYNCHRONOUS_NORMAL_PERSIST",
            "value": 3
        },
        {
            "label": "ENUM_SYNCHRONOUS_OFF_PERSIST",
            "value": 4
        }
    ],
    "type": "integer",
    "visibility": "HideInEngineering"
}
```
