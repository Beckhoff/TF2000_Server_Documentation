# Attribute pragmas are added to the JSON schema. The attributes configured here are hidden.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.Config::IGNORED_PLC_ATTRIBUTES"` |
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
            "symbol": "ADS.Config::IGNORED_PLC_ATTRIBUTES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::IGNORED_PLC_ATTRIBUTES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::IGNORED_PLC_ATTRIBUTES=' +
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
[
    "DisplayMinValue",
    "DisplayMaxValue",
    "DisplayMinValueX64",
    "DisplayMaxValueX64",
    "LowerBorder",
    "UpperBorder",
    "TcRpcEnable",
    "TcGenerateDeRefType",
    "TcHmiSymbol.ReadOnly",
    "TcHmiSymbol.AddSymbol",
    "TcHmiSymbol.AddSymbol.UserGroups",
    "TcHmiSymbol.AddSymbol.UserGroups.Read",
    "TcHmiSymbol.AddSymbol.Hidden",
    "to_string_function",
    "to_wstring_function"
]
```

## JSON schema

```json
{
    "default": [
        "DisplayMinValue",
        "DisplayMaxValue",
        "DisplayMinValueX64",
        "DisplayMaxValueX64",
        "LowerBorder",
        "UpperBorder",
        "TcRpcEnable",
        "TcGenerateDeRefType",
        "TcHmiSymbol.ReadOnly",
        "TcHmiSymbol.AddSymbol",
        "TcHmiSymbol.AddSymbol.UserGroups",
        "TcHmiSymbol.AddSymbol.UserGroups.Read",
        "TcHmiSymbol.AddSymbol.Hidden",
        "to_string_function",
        "to_wstring_function"
    ],
    "items": {
        "type": "string"
    },
    "propertyOrder": 5,
    "type": "array",
    "visibility": "HideInEngineering"
}
```
