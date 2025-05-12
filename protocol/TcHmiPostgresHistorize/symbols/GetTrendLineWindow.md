# Retrieves the time window for a specific TrendLineChart.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Full symbol path | `"TcHmiPostgresHistorize.GetTrendLineWindow"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| chartName | string | descChartName |
| xAxisStart | pointInTime |  |
| xAxisEnd | pointInTime |  |
| yAxes | array | descTrendLineAxisY |

## Sample request - WebSocket

Get window for TrendChart named 'MyTrendChart1'
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiPostgresHistorize.GetTrendLineWindow",
            "writeValue": {
                "chartName": "MyTrendChart1",
                "xAxisEnd": "PT10S",
                "xAxisStart": "2016-08-08T09:19:00",
                "yAxes": [
                    {
                        "symbol": "test"
                    },
                    {
                        "symbol": "testINT"
                    }
                ]
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Get window for TrendChart named 'MyTrendChart1'
```javascript
TcHmi.Server.writeSymbol('TcHmiPostgresHistorize.GetTrendLineWindow',
    {
        "chartName": "MyTrendChart1",
        "xAxisEnd": "PT10S",
        "xAxisStart": "2016-08-08T09:19:00",
        "yAxes": [
            {
                "symbol": "test"
            },
            {
                "symbol": "testINT"
            }
        ]
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
            'TcHmiPostgresHistorize.GetTrendLineWindow=' +
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
            "xAxisEnd": {
                "description": "descTrendLineAxisEndX",
                "format": "date-time",
                "type": "string"
            },
            "xAxisStart": {
                "description": "descTrendLineAxisStartX",
                "format": "date-time",
                "type": "string"
            }
        },
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "chartName": {
                "description": "descChartName",
                "type": "string"
            },
            "xAxisEnd": {
                "$ref": "#/definitions/pointInTime"
            },
            "xAxisStart": {
                "$ref": "#/definitions/pointInTime"
            },
            "yAxes": {
                "description": "descTrendLineAxisY",
                "items": {
                    "additionalProperties": false,
                    "properties": {
                        "symbol": {
                            "description": "descSymbolName",
                            "type": "string"
                        }
                    },
                    "required": [
                        "symbol"
                    ],
                    "type": "object"
                },
                "type": "array"
            }
        },
        "required": [
            "chartName",
            "yAxes",
            "xAxisStart"
        ],
        "type": "object"
    }
}
```
