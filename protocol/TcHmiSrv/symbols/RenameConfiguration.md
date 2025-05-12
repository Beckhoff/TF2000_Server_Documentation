# Rename configuration.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"RenameConfiguration"` |
| Category | configurationsAndFilesystem |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| old | string |
| new | string |

## Sample request - WebSocket

Rename configuration 'remote' to 'cx9020'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "RenameConfiguration",
            "writeValue": {
                "new": "cx9020",
                "old": "remote"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Rename configuration 'remote' to 'cx9020'.
```javascript
TcHmi.Server.writeSymbol('RenameConfiguration',
    {
        "new": "cx9020",
        "old": "remote"
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
            'RenameConfiguration=' +
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
            "new": {
                "type": "string"
            },
            "old": {
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
