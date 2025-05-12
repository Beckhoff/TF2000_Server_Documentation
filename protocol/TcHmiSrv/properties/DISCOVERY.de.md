# Änderung wird nach Server-Neustart aktiv

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::DISCOVERY"` |
| Kategorie | webserver |
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
            "symbol": "TcHmiSrv.Config::DISCOVERY"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DISCOVERY', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DISCOVERY=' +
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
| `0` | Deaktiviert |
| `1` | Auf standard SSDP-Port aktiviert (1900) |
| `2` | Auf alternativem Port aktiviert (1910) |

## JSON-Schema

```json
{
    "category": "webserver",
    "default": 1,
    "enum": [
        0,
        1,
        2
    ],
    "options": [
        {
            "label": "DISCOVERY_0_DISABLED",
            "value": 0
        },
        {
            "label": "DISCOVERY_1_ENABLED",
            "value": 1
        },
        {
            "label": "DISCOVERY_2_ALTERNATIVE",
            "value": 2
        }
    ],
    "type": "integer"
}
```
