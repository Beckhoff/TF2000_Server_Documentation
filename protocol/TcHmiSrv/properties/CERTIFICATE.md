# PEM or PFX formatted certificate.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::CERTIFICATE"` |
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
            "symbol": "TcHmiSrv.Config::CERTIFICATE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::CERTIFICATE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::CERTIFICATE=' +
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
    "configDescription": "DESC_PEM_CERT",
    "default": "",
    "format": "certificate",
    "propertyOrder": 6,
    "type": "string"
}
```
