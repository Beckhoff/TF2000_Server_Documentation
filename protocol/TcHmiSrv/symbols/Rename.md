# Rename a map entry.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"Rename"` |
| Category | configurationsAndFilesystem |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| domain | string | Extension domain. |
| configuration | string | Configuration name. |
| old | string | Path to the old entry. |
| new | string | Path to the new entry. |

## Sample request - WebSocket

Rename symbol `test` to `stepCount`.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Rename",
            "writeValue": {
                "domain": "TcHmiSrv",
                "new": "SYMBOLS::stepCount",
                "old": "SYMBOLS::test"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Rename symbol `test` to `stepCount`.
```javascript
TcHmi.Server.writeSymbol('Rename',
    {
        "domain": "TcHmiSrv",
        "new": "SYMBOLS::stepCount",
        "old": "SYMBOLS::test"
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
            'Rename=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "configurationsAndFilesystem",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "properties": {
            "configuration": {
                "default": "default",
                "description": "Configuration name.",
                "type": "string"
            },
            "domain": {
                "description": "Extension domain.",
                "type": "string"
            },
            "new": {
                "description": "Path to the new entry.",
                "type": "string"
            },
            "old": {
                "description": "Path to the old entry.",
                "type": "string"
            }
        },
        "required": [
            "old",
            "new"
        ],
        "type": "object"
    }
}
```
