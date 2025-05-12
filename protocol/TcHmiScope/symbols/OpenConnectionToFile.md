# Get Data for ScopeChart named 'MyScopeYT Chart'.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.OpenConnectionToFile"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| uploadFileInformation | object |  |

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
            "symbol": "TcHmiScope.OpenConnectionToFile",
            "writeValue": {
                "controlName": "MyScopeYT Chart",
                "uploadFileInformation": {
                    "chartName": "Chart",
                    "extensionName": "TcHmiScope",
                    "fileName": "Test.svdx",
                    "guid": "2997437c-6969-4fe0-8bc2-3275125f6ebd",
                    "persist": true,
                    "userName": "Julia"
                }
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get Data for ScopeChart named 'MyScopeYT Chart'.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.OpenConnectionToFile',
    {
        "controlName": "MyScopeYT Chart",
        "uploadFileInformation": {
            "chartName": "Chart",
            "extensionName": "TcHmiScope",
            "fileName": "Test.svdx",
            "guid": "2997437c-6969-4fe0-8bc2-3275125f6ebd",
            "persist": true,
            "userName": "Julia"
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
            'TcHmiScope.OpenConnectionToFile=' +
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
            "chart": {
                "description": "Chart name out of the scope record file.",
                "type": "string"
            },
            "name": {
                "description": "The full path of the scope record file.",
                "type": "string"
            }
        },
        "required": [
            "name",
            "chart"
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
            },
            "uploadFileInformation": {
                "properties": {
                    "chartName": {
                        "description": "Name of chart to show.",
                        "type": "string"
                    },
                    "extensionName": {
                        "description": "Name of extension.",
                        "type": "string"
                    },
                    "fileName": {
                        "description": "Name of file to connect to.",
                        "type": "string"
                    },
                    "guid": {
                        "description": "Guid of file",
                        "type": "string"
                    },
                    "persist": {
                        "description": "Whether to delete the file after extension shutdown. ",
                        "type": "boolean"
                    },
                    "userName": {
                        "description": "Name of user.",
                        "type": "string"
                    }
                },
                "required": [
                    "extensionName",
                    "userName",
                    "fileName",
                    "chartName",
                    "guid",
                    "persist"
                ],
                "type": "object"
            }
        },
        "required": [
            "controlName",
            "uploadFileInformation"
        ],
        "type": "object"
    }
}
```
