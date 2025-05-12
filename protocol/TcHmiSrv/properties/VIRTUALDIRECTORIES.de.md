# Virtuelle Verzeichnisse werden verwendet, um anzugeben, welche Ordnerpfade des Dateisystems über den Webserver bereitgestellt werden sollen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::VIRTUALDIRECTORIES"` |
| Sichtbarkeit | AlwaysShow |
| Standardmäßig in jeder Konfiguration enthalten | Ja |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSrv.Config::VIRTUALDIRECTORIES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::VIRTUALDIRECTORIES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::VIRTUALDIRECTORIES=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Minimale Anzahl von Einträgen | 1 |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
{
    "/": "www"
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "format": "filename",
        "type": "string"
    },
    "default": {
        "/": "www"
    },
    "defaultConfigurable": true,
    "minProperties": 1,
    "type": "object"
}
```
