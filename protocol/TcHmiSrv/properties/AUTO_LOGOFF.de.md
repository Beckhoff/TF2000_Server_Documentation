# Kann für einzelne Benutzerkonten überschrieben werden. Dieser Wert wird verwendet, wenn für den aktuellen Benutzer kein anderer Wert angegeben ist. Achten Sie darauf, dass das Cookie-Ablaufdatum und die Zeit der automatischen Abmeldung nicht im Widerspruch zueinander stehen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::AUTO_LOGOFF"` |
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
            "symbol": "TcHmiSrv.Config::AUTO_LOGOFF"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::AUTO_LOGOFF', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::AUTO_LOGOFF=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Format | timespan |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"P30D"` |

## JSON-Schema

```json
{
    "category": "security",
    "default": "P30D",
    "format": "timespan",
    "propertyOrder": 2,
    "type": "string"
}
```
