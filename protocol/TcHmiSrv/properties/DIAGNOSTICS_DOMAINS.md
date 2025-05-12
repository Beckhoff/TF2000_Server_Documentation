# Logging diagnostics data are useful to diagnose problems but they have a negative impact on performance.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::DIAGNOSTICS_DOMAINS"` |
| Category | advanced |
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
            "symbol": "TcHmiSrv.Config::DIAGNOSTICS_DOMAINS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DIAGNOSTICS_DOMAINS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DIAGNOSTICS_DOMAINS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"array"` |
| Implicit access is allowed | Yes |

## Default value

```json
[]
```

## JSON schema

```json
{
    "category": "advanced",
    "default": [],
    "items": {
        "minLength": 1,
        "optionMethod": {
            "symbol": "ListDomains"
        },
        "type": "string"
    },
    "type": "array"
}
```
