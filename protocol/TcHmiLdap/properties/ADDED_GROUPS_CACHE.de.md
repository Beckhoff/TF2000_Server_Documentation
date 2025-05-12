# Dieser Cache wird benötigt, um Nutzergruppen, die basierend auf Gruppen-Mappings konfiguriert werden, wieder korrekt entfernen zu können.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Vollständiger Symbol-Pfad | `"TcHmiLdap.Config::ADDED_GROUPS_CACHE"` |
| Kategorie | integration |
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
            "symbol": "TcHmiLdap.Config::ADDED_GROUPS_CACHE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::ADDED_GROUPS_CACHE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::ADDED_GROUPS_CACHE=' +
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
        "items": {
            "optionMethod": {
                "symbol": "TcHmiSrv.Config::USERGROUPS"
            },
            "type": "string"
        },
        "type": "array",
        "uniqueItems": true
    },
    "category": "integration",
    "configDescription": "DESC_ADDED_GROUPS_CACHE",
    "propertyOrder": 21,
    "type": "object",
    "visibility": "HideInEngineering"
}
```
