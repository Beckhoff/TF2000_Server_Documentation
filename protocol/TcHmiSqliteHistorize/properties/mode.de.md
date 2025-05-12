# Die Einstellungen Synchronisation aus und Aufzeichnung im flüchtigen Speicher können die Datenbank korrumpieren.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteHistorize.Config::mode"` |
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
            "symbol": "TcHmiSqliteHistorize.Config::mode"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSqliteHistorize.Config::mode', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSqliteHistorize.Config::mode=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `3` |

## Optionen

| Wert | Label |
| ---- | ----- |
| `0` | Synchronisation: extra; Aufzeichnungsart: persistent |
| `1` | Synchronisation: vollständig; Aufzeichnungsart: persistent |
| `2` | Synchronisation: vollständig; Aufzeichnungsart: flüchtiger Speicher |
| `3` | Synchronisation: normal; Aufzeichnungsart: persistent |
| `4` | Synchronisation: aus; Aufzeichnungsart: persistent |
| `5` | Synchronisation: aus; Aufzeichnungsart: flüchtiger Speicher |

## JSON-Schema

```json
{
    "configDescription": "descMode",
    "default": 3,
    "enum": [
        0,
        1,
        2,
        3,
        4,
        5
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
            "label": "ENUM_SYNCHRONOUS_FULL_MEMORY",
            "value": 2
        },
        {
            "label": "ENUM_SYNCHRONOUS_NORMAL_PERSIST",
            "value": 3
        },
        {
            "label": "ENUM_SYNCHRONOUS_OFF_PERSIST",
            "value": 4
        },
        {
            "label": "ENUM_SYNCHRONOUS_OFF_MEMORY",
            "value": 5
        }
    ],
    "propertyOrder": 7,
    "type": "integer",
    "visibility": "HideInEngineering"
}
```
