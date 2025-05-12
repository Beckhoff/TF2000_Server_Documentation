# Sicherheitseinstellungen

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "additionalProperties": false,
    "properties": {
        "acceptAllServerCertificates": {
            "default": true,
            "type": "boolean"
        },
        "acceptSelfSignedCertificates": {
            "default": true,
            "type": "boolean"
        },
        "authEnabled": {
            "default": false,
            "type": "boolean"
        },
        "certificateTrust": {
            "acceptFileTypes": [
                ".der"
            ],
            "default": "",
            "format": "certificate",
            "type": "string"
        },
        "clientCertificate": {
            "acceptFileTypes": [
                ".der"
            ],
            "default": "",
            "format": "certificate",
            "type": "string"
        },
        "clientPrivatekey": {
            "acceptFileTypes": [
                ".pem"
            ],
            "default": "",
            "format": "base64",
            "type": "string"
        },
        "globalPassword": {
            "default": "",
            "format": "masked",
            "type": "string"
        },
        "globalUser": {
            "default": "",
            "type": "string"
        },
        "policyMode": {
            "enum": [
                "http://opcfoundation.org/UA/SecurityPolicy#None",
                "http://opcfoundation.org/UA/SecurityPolicy#Basic128Rsa15",
                "http://opcfoundation.org/UA/SecurityPolicy#Basic256",
                "http://opcfoundation.org/UA/SecurityPolicy#Basic256Sha256"
            ],
            "options": [
                {
                    "label": "none",
                    "value": "http://opcfoundation.org/UA/SecurityPolicy#None"
                },
                {
                    "label": "Basic128Rsa15",
                    "value": "http://opcfoundation.org/UA/SecurityPolicy#Basic128Rsa15"
                },
                {
                    "label": "Basic256",
                    "value": "http://opcfoundation.org/UA/SecurityPolicy#Basic256"
                },
                {
                    "label": "Basic256Sha256",
                    "value": "http://opcfoundation.org/UA/SecurityPolicy#Basic256Sha256"
                }
            ],
            "type": "string"
        },
        "securityMode": {
            "default": 1,
            "enum": [
                1,
                2,
                3
            ],
            "options": [
                {
                    "label": "none",
                    "value": 1
                },
                {
                    "label": "sign",
                    "value": 2
                },
                {
                    "label": "signAndEncrypt",
                    "value": 3
                }
            ],
            "type": "integer"
        },
        "useGlobalUaUser": {
            "default": true,
            "description": "descUseGlobalUaUser",
            "type": "boolean"
        },
        "useHmiServerCertificate": {
            "default": false,
            "type": "boolean"
        }
    },
    "required": [
        "acceptAllServerCertificates",
        "acceptSelfSignedCertificates",
        "authEnabled",
        "certificateTrust",
        "clientCertificate",
        "clientPrivatekey",
        "globalPassword",
        "globalUser",
        "policyMode",
        "securityMode",
        "useGlobalUaUser",
        "useHmiServerCertificate"
    ],
    "type": "object"
}
```
