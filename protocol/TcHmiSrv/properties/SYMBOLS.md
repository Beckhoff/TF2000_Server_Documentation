# Mapped symbols are used to grant access to internal symbols of a domain.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::SYMBOLS"` |
| Category | symbols |
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
            "symbol": "TcHmiSrv.Config::SYMBOLS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::SYMBOLS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::SYMBOLS=' +
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
    "UserSelectType": {
        "ACCESS": 3,
        "DOMAIN": "TcHmiSrv",
        "DYNAMIC": false,
        "HIDDEN": true,
        "MAPPING": "Config::USERSELECTTYPE",
        "SCHEMA": {
            "category": "security",
            "default": 0,
            "description": "DESC_USERSELECTTYPE",
            "enum": [
                0,
                1
            ],
            "options": [
                {
                    "label": "ENUM_COMBOBOX",
                    "value": 0
                },
                {
                    "label": "ENUM_TEXTFIELD",
                    "value": 1
                }
            ],
            "propertyOrder": 14,
            "type": "integer"
        },
        "USEMAPPING": true
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "$ref": "tchmi:server#/definitions/symbol"
    },
    "category": "symbols",
    "configDescription": "DESC_SYMBOLS",
    "default": {
        "UserSelectType": {
            "ACCESS": 3,
            "DOMAIN": "TcHmiSrv",
            "DYNAMIC": false,
            "HIDDEN": true,
            "MAPPING": "Config::USERSELECTTYPE",
            "SCHEMA": {
                "category": "security",
                "default": 0,
                "description": "DESC_USERSELECTTYPE",
                "enum": [
                    0,
                    1
                ],
                "options": [
                    {
                        "label": "ENUM_COMBOBOX",
                        "value": 0
                    },
                    {
                        "label": "ENUM_TEXTFIELD",
                        "value": 1
                    }
                ],
                "propertyOrder": 14,
                "type": "integer"
            },
            "USEMAPPING": true
        }
    },
    "type": "object"
}
```
