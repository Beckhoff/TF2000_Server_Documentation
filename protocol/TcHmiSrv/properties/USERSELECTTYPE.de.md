# Wenn es nur wenige Benutzerkonten gibt, kann die Auswahl des Benutzerkontos über ein Listbox den Anmeldevorgang vereinfachen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::USERSELECTTYPE"` |
| Kategorie | security |
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
            "symbol": "TcHmiSrv.Config::USERSELECTTYPE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::USERSELECTTYPE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::USERSELECTTYPE=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Aufzählungstyp | `"integer"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `0` |

## Optionen

| Wert | Label |
| ---- | ----- |
| `0` | Listbox |
| `1` | Textfeld |

## JSON-Schema

```json
{
    "category": "security",
    "default": 0,
    "enum": [
        0,
        1
    ],
    "options": [
        {
            "label": "ENUM_COMBOBOX",
            "value": 0
        },
        {
            "label": "ENUM_TEXTFIELD",
            "value": 1
        }
    ],
    "propertyOrder": 14,
    "type": "integer"
}
```
