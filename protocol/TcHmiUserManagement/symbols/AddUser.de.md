# Add or update user.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.AddUser"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| userName | string | Name of the user. |
| password | string | Password of the user. Only a hash will be stored. |
| enabled | boolean | Indicates if the user can be used or not. |

## Beispiel-Anfrage - WebSocket

Add user `test`.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiUserManagement.AddUser",
            "writeValue": {
                "password": "YwboLB~[65H",
                "userName": "test"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Add user `test`.
```javascript
TcHmi.Server.writeSymbol('TcHmiUserManagement.AddUser',
    {
        "password": "YwboLB~[65H",
        "userName": "test"
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
            'TcHmiUserManagement.AddUser=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true
    },
    "writeValue": {
        "properties": {
            "enabled": {
                "description": "Indicates if the user can be used or not.",
                "type": "boolean"
            },
            "password": {
                "description": "Password of the user. Only a hash will be stored.",
                "format": "masked",
                "type": "string"
            },
            "userName": {
                "description": "Name of the user.",
                "type": "string"
            }
        },
        "required": [
            "userName",
            "password"
        ],
        "type": "object"
    }
}
```
