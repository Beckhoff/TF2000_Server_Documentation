# Get Data for a specific ScopeChart.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.SaveCurrentRecord"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| scopeConfigName | string | Name of the config file. |
| persist | boolean | Whether a file should be persisted (after shutdown of the extension the file will be deleted). |
| replace | boolean | Whether to overwrite a file (the old file will be deleted). |

## Beispiel-Anfrage - WebSocket

Get Data for ScopeChart named 'MyScopeYT Chart'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.SaveCurrentRecord",
            "writeValue": {
                "persist": true,
                "replace": true,
                "scopeConfigName": "Test"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get Data for ScopeChart named 'MyScopeYT Chart'.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.SaveCurrentRecord',
    {
        "persist": true,
        "replace": true,
        "scopeConfigName": "Test"
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
            'TcHmiScope.SaveCurrentRecord=' +
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
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "persist": {
                "description": "Whether a file should be persisted (after shutdown of the extension the file will be deleted).",
                "type": "boolean"
            },
            "replace": {
                "description": "Whether to overwrite a file (the old file will be deleted).",
                "type": "boolean"
            },
            "scopeConfigName": {
                "description": "Name of the config file.",
                "type": "string"
            }
        },
        "required": [
            "scopeConfigName"
        ],
        "type": "object"
    }
}
```
