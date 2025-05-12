# Get an array containing recording time and its data point for each historized symbol.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Full symbol path | `"TcHmiSqliteHistorize.GetTrendLineData"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| chartName | string | descChartName |
| xAxisStart | stringTypeArray |  |
| xAxisEnd | stringTypeArray |  |
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
            "symbol": "TcHmiSqliteHistorize.GetTrendLineData",
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
TcHmi.Server.writeSymbol('TcHmiSqliteHistorize.GetTrendLineData',
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
            'TcHmiSqliteHistorize.GetTrendLineData=' +
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
                                "type": "number"
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
                "$ref": "#/definitions/stringTypeArray"
            },
            "xAxisStart": {
                "$ref": "#/definitions/stringTypeArray"
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
