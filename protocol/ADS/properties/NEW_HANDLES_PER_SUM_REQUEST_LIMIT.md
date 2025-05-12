# TwinCAT's handle buffer is not resized in the middle of a sum request. Creating too many ADS handles in a single sum request causes errors if TwinCAT's handle buffer is full.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.Config::NEW_HANDLES_PER_SUM_REQUEST_LIMIT"` |
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
            "symbol": "ADS.Config::NEW_HANDLES_PER_SUM_REQUEST_LIMIT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::NEW_HANDLES_PER_SUM_REQUEST_LIMIT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::NEW_HANDLES_PER_SUM_REQUEST_LIMIT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `1` |
| Maximum | `1000` |
| Implicit access is allowed | Yes |
| Default value | `100` |

## JSON schema

```json
{
    "default": 100,
    "maximum": 1000,
    "minimum": 1,
    "propertyOrder": 9,
    "type": "integer",
    "visibility": "HideInEngineering"
}
```
