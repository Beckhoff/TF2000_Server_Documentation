# If 'false', check whether the server certificate was issued by a certificate authority trusted by the operating system.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::TRUST_ALL_CERTIFICATES"` |
| Visibility | AlwaysShow |
| Contained in every configuration by default | Yes |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiLdap.Config::TRUST_ALL_CERTIFICATES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::TRUST_ALL_CERTIFICATES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::TRUST_ALL_CERTIFICATES=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"boolean"` |
| Implicit access is allowed | Yes |
| Default value | `False` |

## JSON schema

```json
{
    "configDescription": "DESC_TRUST_ALL_CERTIFICATES",
    "default": false,
    "defaultConfigurable": true,
    "propertyOrder": 4,
    "type": "boolean"
}
```
