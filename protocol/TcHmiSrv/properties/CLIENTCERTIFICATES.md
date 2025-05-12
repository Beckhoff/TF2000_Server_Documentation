# Client certificates in this list can access the server. You can also link certificates to user groups and use them as an alternative login mechanism.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::CLIENTCERTIFICATES"` |
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
            "symbol": "TcHmiSrv.Config::CLIENTCERTIFICATES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

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
| Type | `"array"` |
| Unique items | Yes |
| Implicit access is allowed | Yes |

## JSON schema

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
