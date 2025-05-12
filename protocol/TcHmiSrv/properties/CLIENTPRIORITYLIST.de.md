# IP-Adressen von priorisierten Clients. Wenn das Client-Limit erreicht ist, können diese Clients sich trotzdem verbinden, indem die Verbindung von Clients, die nicht in der Liste sind, getrennt wird.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::CLIENTPRIORITYLIST"` |
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
            "symbol": "TcHmiSrv.Config::CLIENTPRIORITYLIST"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::CLIENTPRIORITYLIST', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::CLIENTPRIORITYLIST=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "category": "webserver",
    "configDescription": "DESC_CLIENTPRIORITYLIST",
    "items": {
        "type": "string"
    },
    "type": "array"
}
```
