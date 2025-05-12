# Zertifikate, Sicherheitsrichtlinien

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |
| Vollständiger Symbol-Pfad | `"TcHmiOpcUa.Config::securitySettings"` |
| Sichtbarkeit | AlwaysShow |
| Standardmäßig in jeder Konfiguration enthalten | Nein |

## Beispiel-Anfrage - WebSocket

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

## Beispiel-Anfrage - JavaScript

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
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

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

## JSON-Schema

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
