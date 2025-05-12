# Update the symbols of the configured PLC for the specified runtime. Set forceUpdate to update even if the PLC hasn't changed.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSystemEngineering"` |
| Vollständiger Symbol-Pfad | `"TcHmiSystemEngineering.UpdateRuntime"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| runtime | string |
| forceUpdate | boolean |

## Beispiel-Anfrage - WebSocket

Update the symbols of configured PLC for runtime 'Runtime1'. Symbols are updated even if the PLC hasn't changed.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSystemEngineering.UpdateRuntime",
            "writeValue": {
                "forceUpdate": true,
                "runtime": "Runtime1"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Update the symbols of configured PLC for runtime 'Runtime1'. Symbols are updated even if the PLC hasn't changed.
```javascript
TcHmi.Server.writeSymbol('TcHmiSystemEngineering.UpdateRuntime',
    {
        "forceUpdate": true,
        "runtime": "Runtime1"
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
            'TcHmiSystemEngineering.UpdateRuntime=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true
    },
    "writeValue": {
        "properties": {
            "forceUpdate": {
                "type": "boolean"
            },
            "runtime": {
                "type": "string"
            }
        },
        "required": [
            "runtime"
        ],
        "type": "object"
    }
}
```
