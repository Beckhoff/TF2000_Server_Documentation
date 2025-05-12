# Defines how complex a schema may be when mapping a symbol. The number of sub-symbols is counted

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::SYMBOL_COMPLEXITY_LIMIT"` |
| Category | advanced |
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
            "symbol": "TcHmiSrv.Config::SYMBOL_COMPLEXITY_LIMIT"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::SYMBOL_COMPLEXITY_LIMIT', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::SYMBOL_COMPLEXITY_LIMIT=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"integer"` |
| Minimum | `1` |
| Implicit access is allowed | Yes |
| Default value | `100` |

## JSON schema

```json
{
    "category": "advanced",
    "configDescription": "DESC_SYMBOL_COMPLEXITY_LIMIT",
    "default": 100,
    "minimum": 1,
    "type": "integer",
    "visibility": "HideInEngineering"
}
```
