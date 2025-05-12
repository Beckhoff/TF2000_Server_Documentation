# Advanced settings for datatype name translation

## General information

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |
| Full symbol path | `"TcHmiOpcUa.Config::advancedSettings"` |
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
            "symbol": "TcHmiOpcUa.Config::advancedSettings"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiOpcUa.Config::advancedSettings', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiOpcUa.Config::advancedSettings=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## Default value

```json
{
    "basic": {
        "arrayCloseReplacement": "_HMI_RESERVED_ARRAYCLOSE_",
        "arrayOpenReplacement": "_HMI_RESERVED_ARRAYOPEN_",
        "asteriskReplacement": "_HMI_RESERVED_ASTERISK_",
        "browseValueSubelements": false,
        "colonReplacement": "_HMI_RESERVED_COLON_",
        "doubleColonReplacement": "_HMI_RESERVED_DOUBLECOLON_",
        "percentReplacement": "_HMI_RESERVED_PERCENT_",
        "verticalLineReplacement": "_HMI_RESERVED_VERTICALLINE_"
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "$ref": "#/definitions/advanced"
    },
    "default": {
        "basic": {
            "arrayCloseReplacement": "_HMI_RESERVED_ARRAYCLOSE_",
            "arrayOpenReplacement": "_HMI_RESERVED_ARRAYOPEN_",
            "asteriskReplacement": "_HMI_RESERVED_ASTERISK_",
            "browseValueSubelements": false,
            "colonReplacement": "_HMI_RESERVED_COLON_",
            "doubleColonReplacement": "_HMI_RESERVED_DOUBLECOLON_",
            "percentReplacement": "_HMI_RESERVED_PERCENT_",
            "verticalLineReplacement": "_HMI_RESERVED_VERTICALLINE_"
        }
    },
    "type": "object"
}
```
