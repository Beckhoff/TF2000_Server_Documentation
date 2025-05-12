# Custom parameters for the Diffie-Hellman (DH) key-exchange.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::TEMPDH"` |
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
            "symbol": "TcHmiSrv.Config::TEMPDH"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::TEMPDH', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::TEMPDH=' +
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
    "configDescription": "DESC_TEMPDH",
    "default": "",
    "format": "base64",
    "propertyOrder": 11,
    "type": "string"
}
```
