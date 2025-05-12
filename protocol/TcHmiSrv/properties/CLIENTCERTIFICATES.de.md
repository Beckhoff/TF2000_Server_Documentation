# Client-Zertifikate in dieser Liste können auf den Server zugreifen. Sie können Zertifikate auch mit Benutzergruppen verknüpfen und diese als alternativen Anmeldemechanismus verwenden.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::CLIENTCERTIFICATES"` |
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
            "symbol": "TcHmiSrv.Config::CLIENTCERTIFICATES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::CLIENTCERTIFICATES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::CLIENTCERTIFICATES=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Duplikate erlaubt | Ja |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "category": "security",
    "items": {
        "properties": {
            "CLIENTCERTIFICATE": {
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
            "DEFAULTUSER": {
                "default": "",
                "optionMethod": {
                    "symbol": "ListUserNames"
                },
                "type": "string"
            },
            "ENABLECLIENTCERTIFICATE": {
                "default": true,
                "type": "boolean"
            }
        },
        "type": "object"
    },
    "propertyOrder": 5,
    "type": "array",
    "uniqueItems": true
}
```
