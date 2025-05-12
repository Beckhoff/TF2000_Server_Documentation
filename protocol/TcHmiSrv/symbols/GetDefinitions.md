# List all definitions of a particular type.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"GetDefinitions"` |
| Category | symbols |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| type | string |
| resolve | string |

## Sample request - WebSocket

Get all project definitions.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetDefinitions",
            "writeValue": {
                "resolve": "AddAllRefs",
                "type": "project"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get all project definitions.
```javascript
TcHmi.Server.writeSymbol('GetDefinitions',
    {
        "resolve": "AddAllRefs",
        "type": "project"
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
            'GetDefinitions=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "symbols",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "properties": {
            "resolve": {
                "default": "None",
                "enum": [
                    "AddAllRefs",
                    "Simplify",
                    "None"
                ],
                "type": "string"
            },
            "type": {
                "default": "general",
                "enum": [
                    "server",
                    "framework",
                    "general",
                    "project"
                ],
                "type": "string"
            }
        },
        "type": "object"
    }
}
```
