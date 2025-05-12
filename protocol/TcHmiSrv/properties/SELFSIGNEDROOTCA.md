# This certificate is used to create self-signed server certificates.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::SELFSIGNEDROOTCA"` |
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
            "symbol": "TcHmiSrv.Config::SELFSIGNEDROOTCA"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::SELFSIGNEDROOTCA', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::SELFSIGNEDROOTCA=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | certificate |
| Implicit access is allowed | Yes |
| Default value | `""` |

## JSON schema

```json
{
    "acceptFileTypes": [
        ".pem",
        ".pfx",
        ".cer",
        ".crt"
    ],
    "category": "security",
    "default": "",
    "format": "certificate",
    "propertyOrder": 7,
    "type": "string"
}
```
