# Certificates, security policies

## General information

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |
| Full symbol path | `"TcHmiOpcUa.Config::securitySettings"` |
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
            "symbol": "TcHmiOpcUa.Config::securitySettings"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiOpcUa.Config::securitySettings', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiOpcUa.Config::securitySettings=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## Default value

```json
{
    "basic": {
        "acceptAllServerCertificates": true,
        "acceptSelfSignedCertificates": true,
        "certificateTrust": "",
        "clientCertificate": "",
        "clientPrivatekey": "",
        "globalPassword": "",
        "globalUser": "",
        "policyMode": "http://opcfoundation.org/UA/SecurityPolicy#None",
        "securityMode": 1,
        "useGlobalUaUser": true,
        "useHmiServerCertificate": false
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "$ref": "#/definitions/security"
    },
    "default": {
        "basic": {
            "acceptAllServerCertificates": true,
            "acceptSelfSignedCertificates": true,
            "certificateTrust": "",
            "clientCertificate": "",
            "clientPrivatekey": "",
            "globalPassword": "",
            "globalUser": "",
            "policyMode": "http://opcfoundation.org/UA/SecurityPolicy#None",
            "securityMode": 1,
            "useGlobalUaUser": true,
            "useHmiServerCertificate": false
        }
    },
    "type": "object"
}
```
