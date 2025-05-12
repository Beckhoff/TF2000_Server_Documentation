# Timeout, nach dem die Ausführung eines Lua-Scripts abgebrochen wird.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiLua"` |
| Vollständiger Symbol-Pfad | `"TcHmiLua.Config::SCRIPT_TIMEOUT"` |
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
            "symbol": "TcHmiLua.Config::SCRIPT_TIMEOUT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLua.Config::SCRIPT_TIMEOUT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLua.Config::SCRIPT_TIMEOUT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | timespan |
| Minimum | `PT5S` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"PT10S"` |

## JSON-Schema

```json
{
    "configDescription": "DESC_SCRIPT_TIMEOUT",
    "default": "PT10S",
    "format": "timespan",
    "formatMinimum": "PT5S",
    "type": "string"
}
```
