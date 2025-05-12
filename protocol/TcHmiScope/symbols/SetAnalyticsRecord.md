# Set a historical records with time range for acquisition with the same target.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.SetAnalyticsRecord"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | Control name. |
| scopeConfig | object | Information for scope config. |
| recordId | number | Record id. |
| recordName | string | Record name. |
| startTime | string | Start time for the record. |
| endTime | string | End time for the record. |

## Sample request - WebSocket

Set a historical records with time range for acquisition with the same target.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.SetAnalyticsRecord",
            "writeValue": {
                "controlName": "MyScopeYT Chart",
                "endTime": "2022-09-19T11:05:40.0821Z",
                "recordName": "Record_1",
                "scopeConfig": {
                    "chart": "YT Chart",
                    "name": "ScopeConfig"
                },
                "startTime": "2022-09-19T11:03:40.0821Z"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Set a historical records with time range for acquisition with the same target.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.SetAnalyticsRecord',
    {
        "controlName": "MyScopeYT Chart",
        "endTime": "2022-09-19T11:05:40.0821Z",
        "recordName": "Record_1",
        "scopeConfig": {
            "chart": "YT Chart",
            "name": "ScopeConfig"
        },
        "startTime": "2022-09-19T11:03:40.0821Z"
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
            'TcHmiScope.SetAnalyticsRecord=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

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
            "controlName": {
                "description": "Control name.",
                "type": "string"
            },
            "endTime": {
                "description": "End time for the record.",
                "format": "date-time",
                "type": "string"
            },
            "recordId": {
                "description": "Record id.",
                "type": "number"
            },
            "recordName": {
                "description": "Record name.",
                "type": "string"
            },
            "scopeConfig": {
                "additionalProperties": false,
                "description": "Information for scope config.",
                "properties": {
                    "chart": {
                        "description": "Chart name out of the scope config.",
                        "type": "string"
                    },
                    "name": {
                        "description": "Name of the scope config.",
                        "type": "string"
                    }
                },
                "required": [
                    "name",
                    "chart"
                ],
                "type": "object"
            },
            "startTime": {
                "description": "Start time for the record.",
                "format": "date-time",
                "type": "string"
            }
        },
        "type": "object"
    }
}
```
