# The most common ports are 636 for TLS and 389 for unencrypted connections.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::PORT"` |
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
            "symbol": "TcHmiLdap.Config::PORT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::PORT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::PORT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `1` |
| Implicit access is allowed | Yes |
| Default value | `389` |

## JSON schema

```json
{
    "default": 389,
    "defaultConfigurable": true,
    "minimum": 1,
    "propertyOrder": 2,
    "type": "integer"
}
```
