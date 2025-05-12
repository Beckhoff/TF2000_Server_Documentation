# Ein Symbol-Mapping ermöglicht den Zugriff auf interne Symbole einer Domäne.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::SYMBOLS"` |
| Kategorie | symbols |
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
            "symbol": "TcHmiSrv.Config::SYMBOLS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::SYMBOLS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::SYMBOLS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
{
    "UserSelectType": {
        "ACCESS": 3,
        "DOMAIN": "TcHmiSrv",
        "DYNAMIC": false,
        "HIDDEN": true,
        "MAPPING": "Config::USERSELECTTYPE",
        "SCHEMA": {
            "category": "security",
            "default": 0,
            "description": "DESC_USERSELECTTYPE",
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
        },
        "USEMAPPING": true
    }
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "$ref": "tchmi:server#/definitions/symbol"
    },
    "category": "symbols",
    "configDescription": "DESC_SYMBOLS",
    "default": {
        "UserSelectType": {
            "ACCESS": 3,
            "DOMAIN": "TcHmiSrv",
            "DYNAMIC": false,
            "HIDDEN": true,
            "MAPPING": "Config::USERSELECTTYPE",
            "SCHEMA": {
                "category": "security",
                "default": 0,
                "description": "DESC_USERSELECTTYPE",
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
            },
            "USEMAPPING": true
        }
    },
    "type": "object"
}
```
