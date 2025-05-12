# Abrufen des Fensters für ein bestimmtes TrendLineChart.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSqliteHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiSqliteHistorize.GetTrendLineWindow"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| chartName | string | descChartName |
| xAxisStart | stringTypeArray |  |
| xAxisEnd | stringTypeArray |  |
| yAxes | array | descTrendLineAxisY |

## Beispiel-Anfrage - WebSocket

Get window for TrendChart named 'MyTrendChart1'
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSqliteHistorize.GetTrendLineWindow",
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

## Beispiel-Anfrage - JavaScript

Get window for TrendChart named 'MyTrendChart1'
```javascript
TcHmi.Server.writeSymbol('TcHmiSqliteHistorize.GetTrendLineWindow',
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
            'TcHmiSqliteHistorize.GetTrendLineWindow=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

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
                "$ref": "#/definitions/stringTypeArray"
            },
            "xAxisStart": {
                "$ref": "#/definitions/stringTypeArray"
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
