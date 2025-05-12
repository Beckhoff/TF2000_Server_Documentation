# Attribut-Pragmas werden zum JSON-Schema hinzugefügt. Die hier konfigurierten Attribute werden ausgeblendet.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.Config::IGNORED_PLC_ATTRIBUTES"` |
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
            "symbol": "ADS.Config::IGNORED_PLC_ATTRIBUTES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::IGNORED_PLC_ATTRIBUTES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::IGNORED_PLC_ATTRIBUTES=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
[
    "DisplayMinValue",
    "DisplayMaxValue",
    "DisplayMinValueX64",
    "DisplayMaxValueX64",
    "LowerBorder",
    "UpperBorder",
    "TcRpcEnable",
    "TcGenerateDeRefType",
    "TcHmiSymbol.ReadOnly",
    "TcHmiSymbol.AddSymbol",
    "TcHmiSymbol.AddSymbol.UserGroups",
    "TcHmiSymbol.AddSymbol.UserGroups.Read",
    "TcHmiSymbol.AddSymbol.Hidden",
    "to_string_function",
    "to_wstring_function"
]
```

## JSON-Schema

```json
{
    "default": [
        "DisplayMinValue",
        "DisplayMaxValue",
        "DisplayMinValueX64",
        "DisplayMaxValueX64",
        "LowerBorder",
        "UpperBorder",
        "TcRpcEnable",
        "TcGenerateDeRefType",
        "TcHmiSymbol.ReadOnly",
        "TcHmiSymbol.AddSymbol",
        "TcHmiSymbol.AddSymbol.UserGroups",
        "TcHmiSymbol.AddSymbol.UserGroups.Read",
        "TcHmiSymbol.AddSymbol.Hidden",
        "to_string_function",
        "to_wstring_function"
    ],
    "items": {
        "type": "string"
    },
    "propertyOrder": 5,
    "type": "array",
    "visibility": "HideInEngineering"
}
```
