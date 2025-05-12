# Retrieves an array of timestamps and data points for the requested symbol(s).

## General information

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Full symbol path | `"TcHmiPostgresHistorize.GetTrendLineData"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| chartName | string | descChartName |
| xAxisStart | pointInTime |  |
| xAxisEnd | pointInTime |  |
| displayWidth | number |  |
| yAxes | array |  |

## Sample request - WebSocket

Get data for TrendLineChart named 'MyTrendChart1'
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiPostgresHistorize.GetTrendLineData",
            "writeValue": {
                "chartName": "MyTrendChart1",
                "displayWidth": 600,
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

Get data for TrendLineChart named 'MyTrendChart1'
```javascript
TcHmi.Server.writeSymbol('TcHmiPostgresHistorize.GetTrendLineData',
    {
        "chartName": "MyTrendChart1",
        "displayWidth": 600,
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
            'TcHmiPostgresHistorize.GetTrendLineData=' +
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
            "axesData": {
                "description": "descAxisData",
                "items": {
                    "items": {
                        "properties": {
                            "error": {
                                "type": "integer"
                            },
                            "flags": {
                                "description": "descAxisDataFlags",
                                "type": "string"
                            },
                            "x": {
                                "description": "descAxisDataX",
                                "format": "date-time",
                                "type": "string"
                            },
                            "y": {
                                "description": "descAxisDataY",
                                "type": "number"
                            }
                        },
                        "type": "object"
                    },
                    "type": "array"
                },
                "type": "array"
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
            "displayWidth": {
                "minimum": 2.0,
                "type": "number"
            },
            "xAxisEnd": {
                "$ref": "#/definitions/pointInTime"
            },
            "xAxisStart": {
                "$ref": "#/definitions/pointInTime"
            },
            "yAxes": {
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
            "xAxisStart",
            "displayWidth"
        ],
        "type": "object"
    }
}
```
