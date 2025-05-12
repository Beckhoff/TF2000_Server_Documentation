# The PLC task is locked for every request. If the request is too large, the PLC cycle time might be exceeded.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.Config::RESPONSE_SIZE_LIMIT"` |
| Visibility | HideInEngineering |
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
            "symbol": "ADS.Config::RESPONSE_SIZE_LIMIT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::RESPONSE_SIZE_LIMIT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::RESPONSE_SIZE_LIMIT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `2048` |
| Implicit access is allowed | Yes |
| Default value | `2097152` |

## JSON schema

```json
{
    "allOf": [
        {
            "$ref": "tchmi:general#/definitions/INT32"
        },
        {
            "default": 2097152,
            "description": "DESC_RESPONSE_SIZE_LIMIT",
            "minimum": 2048,
            "propertyOrder": 7,
            "type": "integer",
            "unit": "byte",
            "visibility": "HideInEngineering"
        }
    ]
}
```
