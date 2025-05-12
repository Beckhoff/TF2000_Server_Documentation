# Multiple authentication extensions can be used at the same time. The default authentication extension is automatically selected on the login page.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"DefaultAuthExtension"` |
| Kategorie | security |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "DefaultAuthExtension",
            "writeValue": "TcHmiUserManagement"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.writeSymbol('DefaultAuthExtension',
    "TcHmiUserManagement",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'DefaultAuthExtension=' +
            data.response.commands[0].readValue);
    }
);
```

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Impliziter Zugriff erlaubt | Ja |
| Default-Wert | `"TcHmiUserManagement"` |

## JSON-Schema

```json
{
    "category": "security",
    "readValue": {
        "default": "TcHmiUserManagement",
        "type": "string"
    }
}
```
