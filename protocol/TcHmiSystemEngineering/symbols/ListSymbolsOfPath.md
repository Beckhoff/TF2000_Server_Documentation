# Get the symbols of the specified adsRuntime in the specified path.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSystemEngineering"` |
| Full symbol path | `"TcHmiSystemEngineering.ListSymbolsOfPath"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| adsRuntime | string |
| path | string |

## Sample request - WebSocket

Get the symbols of adsRuntime 'PLC1
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSystemEngineering.ListSymbolsOfPath",
            "writeValue": {
                "adsRuntime": "PLC1",
                "path": "MAIN::"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get the symbols of adsRuntime 'PLC1
```javascript
TcHmi.Server.writeSymbol('TcHmiSystemEngineering.ListSymbolsOfPath',
    {
        "adsRuntime": "PLC1",
        "path": "MAIN::"
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
            'TcHmiSystemEngineering.ListSymbolsOfPath=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "items": {
            "type": "string"
        },
        "readOnly": true,
        "type": "array"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "adsRuntime": {
                "type": "string"
            },
            "path": {
                "type": "string"
            }
        },
        "required": [
            "adsRuntime",
            "path"
        ],
        "type": "object"
    }
}
```
