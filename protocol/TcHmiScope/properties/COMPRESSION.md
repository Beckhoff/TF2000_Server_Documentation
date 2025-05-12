# Defines whether to compress when downloading a record.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.Config::COMPRESSION"` |
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
            "symbol": "TcHmiScope.Config::COMPRESSION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiScope.Config::COMPRESSION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiScope.Config::COMPRESSION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"boolean"` |
| Implicit access is allowed | Yes |
| Default value | `True` |

## JSON schema

```json
{
    "configDescription": "DESC_COMPRESSION",
    "default": true,
    "propertyOrder": 2,
    "type": "boolean"
}
```
