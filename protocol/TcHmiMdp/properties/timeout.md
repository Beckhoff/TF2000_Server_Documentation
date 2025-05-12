# Timeout for ADS requests.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiMdp"` |
| Full symbol path | `"TcHmiMdp.Config::timeout"` |
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
            "symbol": "TcHmiMdp.Config::timeout"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiMdp.Config::timeout', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiMdp.Config::timeout=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Format | timespan |
| Minimum | `PT0.1S` |
| Implicit access is allowed | Yes |
| Default value | `"PT1S"` |

## JSON schema

```json
{
    "configDescription": "descTimeout",
    "default": "PT1S",
    "format": "timespan",
    "formatMinimum": "PT0.1S",
    "type": "string"
}
```
