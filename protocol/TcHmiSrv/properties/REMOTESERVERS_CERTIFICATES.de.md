# Zertifikate der Remote-Server.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::REMOTESERVERS_CERTIFICATES"` |
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
            "symbol": "TcHmiSrv.Config::REMOTESERVERS_CERTIFICATES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::REMOTESERVERS_CERTIFICATES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::REMOTESERVERS_CERTIFICATES=' +
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
    "configDescription": "DESC_REMOTESERVERS_CERTIFICATES",
    "items": {
        "acceptFileTypes": [
            ".pem",
            ".pfx",
            ".cer",
            ".crt"
        ],
        "configDescription": "DESC_PEM_CERT",
        "default": "",
        "format": "certificate",
        "type": "string"
    },
    "type": "array"
}
```
