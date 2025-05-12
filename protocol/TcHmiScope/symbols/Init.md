# Get Data for a specific ScopeChart.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.Init"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |

## Sample request - WebSocket

Get Data for ScopeChart named 'MyScopeYT Chart'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.Init",
            "writeValue": {
                "controlName": "MyScopeYT Chart"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get Data for ScopeChart named 'MyScopeYT Chart'.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.Init',
    {
        "controlName": "MyScopeYT Chart"
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
            'TcHmiScope.Init=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "initCompleted": {
                "type": "boolean"
            },
            "socketId": {
                "type": "number"
            }
        },
        "required": [
            "socketId"
        ],
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "controlName": {
                "description": "ScopeChart Name.",
                "type": "string"
            }
        },
        "required": [
            "controlName"
        ],
        "type": "object"
    }
}
```
