# Call an authentication extension's RemoveUser function and subsequently remove the associated USERGROUPUSERS entry.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"RemoveUser"` |
| Kategorie | usersAndSessions |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| domain | string | Domain name of the authentication extension |
| userName | string | Name of the user without domain prefix |

## Beispiel-Anfrage - WebSocket

Remove user 'Operator' from the 'TcHmiUserManagement' authentication domain.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "RemoveUser",
            "writeValue": {
                "domain": "TcHmiUserManagement",
                "userName": "Operator"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Remove user 'Operator' from the 'TcHmiUserManagement' authentication domain.
```javascript
TcHmi.Server.writeSymbol('RemoveUser',
    {
        "domain": "TcHmiUserManagement",
        "userName": "Operator"
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'RemoveUser=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "properties": {
            "domain": {
                "description": "Domain name of the authentication extension",
                "type": "string"
            },
            "userName": {
                "description": "Name of the user without domain prefix",
                "type": "string"
            }
        },
        "required": [
            "domain",
            "userName"
        ],
        "type": "object"
    }
}
```
