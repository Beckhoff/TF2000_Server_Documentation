# Leave empty to use client locale.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::DEFAULTLOCALE"` |
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
            "symbol": "TcHmiSrv.Config::DEFAULTLOCALE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFAULTLOCALE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFAULTLOCALE=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "allOf": [
        {
            "oneOf": [
                {
                    "$ref": "tchmi:general#/definitions/Locale"
                },
                {
                    "default": "client",
                    "enum": [
                        "client"
                    ],
                    "type": "string"
                }
            ]
        },
        {
            "configDescription": "DESC_LOCALE"
        }
    ]
}
```
