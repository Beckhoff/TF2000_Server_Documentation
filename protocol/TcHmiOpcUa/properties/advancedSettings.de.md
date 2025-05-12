# Erweiterte Einstellungen für die Übersetzung von Datentypnamen

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |
| Vollständiger Symbol-Pfad | `"TcHmiOpcUa.Config::advancedSettings"` |
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
            "symbol": "TcHmiOpcUa.Config::advancedSettings"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiOpcUa.Config::advancedSettings', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiOpcUa.Config::advancedSettings=' +
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
    "basic": {
        "arrayCloseReplacement": "_HMI_RESERVED_ARRAYCLOSE_",
        "arrayOpenReplacement": "_HMI_RESERVED_ARRAYOPEN_",
        "asteriskReplacement": "_HMI_RESERVED_ASTERISK_",
        "browseValueSubelements": false,
        "colonReplacement": "_HMI_RESERVED_COLON_",
        "doubleColonReplacement": "_HMI_RESERVED_DOUBLECOLON_",
        "percentReplacement": "_HMI_RESERVED_PERCENT_",
        "verticalLineReplacement": "_HMI_RESERVED_VERTICALLINE_"
    }
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "$ref": "#/definitions/advanced"
    },
    "default": {
        "basic": {
            "arrayCloseReplacement": "_HMI_RESERVED_ARRAYCLOSE_",
            "arrayOpenReplacement": "_HMI_RESERVED_ARRAYOPEN_",
            "asteriskReplacement": "_HMI_RESERVED_ASTERISK_",
            "browseValueSubelements": false,
            "colonReplacement": "_HMI_RESERVED_COLON_",
            "doubleColonReplacement": "_HMI_RESERVED_DOUBLECOLON_",
            "percentReplacement": "_HMI_RESERVED_PERCENT_",
            "verticalLineReplacement": "_HMI_RESERVED_VERTICALLINE_"
        }
    },
    "type": "object"
}
```
