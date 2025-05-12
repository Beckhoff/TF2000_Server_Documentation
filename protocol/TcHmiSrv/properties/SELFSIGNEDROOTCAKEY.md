# This key is used to decrypt the root certificate.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::SELFSIGNEDROOTCAKEY"` |
| Category | security |
| Visibility | AlwaysShow |
| Contained in every configuration by default | No |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSrv.Config::SELFSIGNEDROOTCAKEY"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::SELFSIGNEDROOTCAKEY', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::SELFSIGNEDROOTCAKEY=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | base64 |
| Implicit access is allowed | Yes |
| Default value | `""` |

## JSON schema

```json
{
    "category": "security",
    "default": "",
    "format": "base64",
    "propertyOrder": 8,
    "type": "string"
}
```
