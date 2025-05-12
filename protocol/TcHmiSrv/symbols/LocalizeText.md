# The localized text.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"LocalizeText"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Localize the language variable `FILE_STORE` to the currently set language.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "LocalizeText",
            "writeValue": {
                "domain": "TcHmiSrv",
                "name": "FILE_STORE",
                "params": {
                    "0": "test.txt"
                }
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Localize the language variable `FILE_STORE` to the currently set language.
```javascript
TcHmi.Server.writeSymbol('LocalizeText',
    {
        "domain": "TcHmiSrv",
        "name": "FILE_STORE",
        "params": {
            "0": "test.txt"
        }
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'LocalizeText=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "description": "The localized text.",
        "function": true,
        "type": "string"
    },
    "writeValue": {
        "oneOf": [
            {
                "$ref": "tchmi:server#/definitions/alarm"
            },
            {
                "$ref": "tchmi:server#/definitions/message"
            },
            {
                "description": "Localizable object.",
                "properties": {
                    "domain": {
                        "type": "string"
                    },
                    "name": {
                        "type": "string"
                    },
                    "params": {
                        "additionalProperties": {},
                        "type": "object"
                    }
                },
                "required": [
                    "name",
                    "domain"
                ],
                "type": "object"
            }
        ]
    }
}
```
