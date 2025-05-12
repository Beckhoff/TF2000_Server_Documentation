# Certificates of the remote servers.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::REMOTESERVERS_CERTIFICATES"` |
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
            "symbol": "TcHmiSrv.Config::REMOTESERVERS_CERTIFICATES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

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
| Type | `"array"` |
| Implicit access is allowed | Yes |

## JSON schema

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
