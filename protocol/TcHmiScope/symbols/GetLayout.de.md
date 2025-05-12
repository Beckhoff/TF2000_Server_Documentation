# Get Data for a specific ScopeChart. Symbols must be called from the same socket as OpenConnection.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.GetLayout"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |

## Beispiel-Anfrage - WebSocket

Get Data for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.GetLayout",
            "writeValue": {
                "controlName": "MyScopeYT Chart",
                "scopeConfig": {
                    "chart": "YT Chart",
                    "name": "ScopeConfig"
                }
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get Data for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.GetLayout',
    {
        "controlName": "MyScopeYT Chart",
        "scopeConfig": {
            "chart": "YT Chart",
            "name": "ScopeConfig"
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
            'TcHmiScope.GetLayout=' +
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
            "backgroundColor": {
                "type": "string"
            },
            "chartType": {
                "type": "string"
            },
            "charts": {
                "items": {
                    "oneOf": [
                        {
                            "properties": {
                                "backgroundImage": {
                                    "properties": {
                                        "dimensions": {
                                            "$ref": "#/definitions/dimensions"
                                        },
                                        "image": {
                                            "type": "string"
                                        },
                                        "position": {
                                            "$ref": "#/definitions/position"
                                        }
                                    },
                                    "type": "object"
                                },
                                "canvas": {
                                    "properties": {
                                        "backgroundColor": {
                                            "type": "string"
                                        },
                                        "dimensions": {
                                            "$ref": "#/definitions/dimensions"
                                        },
                                        "position": {
                                            "$ref": "#/definitions/position"
                                        }
                                    },
                                    "type": "object"
                                },
                                "dimensions": {
                                    "$ref": "#/definitions/dimensions"
                                },
                                "graphs": {
                                    "items": {
                                        "properties": {
                                            "antialias": {
                                                "type": "boolean"
                                            },
                                            "capColor": {
                                                "type": "string"
                                            },
                                            "capSize": {
                                                "type": "number"
                                            },
                                            "fillColor": {
                                                "type": "string"
                                            },
                                            "fillMode": {
                                                "type": "string"
                                            },
                                            "fillTransparency": {
                                                "type": "number"
                                            },
                                            "graphName": {
                                                "type": "string"
                                            },
                                            "graphType": {
                                                "type": "string"
                                            },
                                            "lineColor": {
                                                "type": "string"
                                            },
                                            "lineStyle": {
                                                "type": "string"
                                            },
                                            "lineWidth": {
                                                "type": "string"
                                            },
                                            "markColor": {
                                                "type": "string"
                                            },
                                            "markStyle": {
                                                "type": "string"
                                            },
                                            "markWidth": {
                                                "type": "number"
                                            },
                                            "marks": {
                                                "type": "boolean"
                                            },
                                            "showEndCap": {
                                                "type": "boolean"
                                            },
                                            "showStartCap": {
                                                "type": "boolean"
                                            }
                                        },
                                        "required": [
                                            "graphName",
                                            "graphType",
                                            "marks",
                                            "lineColor",
                                            "lineWidth",
                                            "lineStyle",
                                            "markColor",
                                            "markWidth",
                                            "markStyle",
                                            "antialias"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "gridSize": {
                                    "properties": {
                                        "dimensions": {
                                            "$ref": "#/definitions/dimensions"
                                        },
                                        "position": {
                                            "$ref": "#/definitions/position"
                                        }
                                    },
                                    "type": "object"
                                },
                                "headline": {
                                    "properties": {
                                        "color": {
                                            "type": "string"
                                        },
                                        "dimensions": {
                                            "$ref": "#/definitions/dimensions"
                                        },
                                        "fontSize": {
                                            "type": "number"
                                        },
                                        "label": {
                                            "type": "string"
                                        },
                                        "position": {
                                            "$ref": "#/definitions/position"
                                        }
                                    },
                                    "required": [
                                        "dimensions",
                                        "position",
                                        "label",
                                        "color",
                                        "fontSize"
                                    ],
                                    "type": "object"
                                },
                                "horizontalAxis": {
                                    "items": {
                                        "properties": {
                                            "color": {
                                                "type": "string"
                                            },
                                            "dimensions": {
                                                "$ref": "#/definitions/dimensions"
                                            },
                                            "grid": {
                                                "properties": {
                                                    "color": {
                                                        "type": "string"
                                                    },
                                                    "lineWidth": {
                                                        "type": "number"
                                                    },
                                                    "ticks": {
                                                        "type": "number"
                                                    },
                                                    "visible": {
                                                        "type": "boolean"
                                                    }
                                                },
                                                "required": [
                                                    "visible",
                                                    "ticks",
                                                    "color",
                                                    "lineWidth"
                                                ],
                                                "type": "object"
                                            },
                                            "headline": {
                                                "properties": {
                                                    "color": {
                                                        "type": "string"
                                                    },
                                                    "dimensions": {
                                                        "$ref": "#/definitions/dimensions"
                                                    },
                                                    "fontSize": {
                                                        "type": "number"
                                                    },
                                                    "label": {
                                                        "type": "string"
                                                    },
                                                    "position": {
                                                        "$ref": "#/definitions/position"
                                                    }
                                                },
                                                "required": [
                                                    "dimensions",
                                                    "position",
                                                    "label",
                                                    "color",
                                                    "fontSize"
                                                ],
                                                "type": "object"
                                            },
                                            "labels": {
                                                "items": {
                                                    "properties": {
                                                        "color": {
                                                            "type": "string"
                                                        },
                                                        "dimensions": {
                                                            "$ref": "#/definitions/dimensions"
                                                        },
                                                        "fontSize": {
                                                            "type": "number"
                                                        },
                                                        "label": {
                                                            "type": "string"
                                                        },
                                                        "position": {
                                                            "$ref": "#/definitions/position"
                                                        }
                                                    },
                                                    "required": [
                                                        "dimensions",
                                                        "position",
                                                        "label",
                                                        "color",
                                                        "fontSize"
                                                    ],
                                                    "type": "object"
                                                },
                                                "type": "array"
                                            },
                                            "lineWidth": {
                                                "type": "number"
                                            },
                                            "position": {
                                                "$ref": "#/definitions/position"
                                            },
                                            "subGrid": {
                                                "properties": {
                                                    "color": {
                                                        "type": "string"
                                                    },
                                                    "lineWidth": {
                                                        "type": "number"
                                                    },
                                                    "ticks": {
                                                        "dimensions": {
                                                            "$ref": "#/definitions/dimensions"
                                                        },
                                                        "position": {
                                                            "$ref": "#/definitions/position"
                                                        },
                                                        "type": "number"
                                                    },
                                                    "visible": {
                                                        "type": "boolean"
                                                    }
                                                },
                                                "required": [
                                                    "visible",
                                                    "ticks",
                                                    "color",
                                                    "lineWidth"
                                                ],
                                                "type": "object"
                                            },
                                            "visible": {
                                                "type": "boolean"
                                            },
                                            "visibleTicks": {
                                                "type": "boolean"
                                            }
                                        },
                                        "required": [
                                            "visible",
                                            "dimensions",
                                            "position"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "position": {
                                    "$ref": "#/definitions/position"
                                },
                                "preferredSize": {
                                    "$ref": "#/definitions/dimensions"
                                },
                                "verticalAxis": {
                                    "items": {
                                        "properties": {
                                            "color": {
                                                "type": "string"
                                            },
                                            "dimensions": {
                                                "$ref": "#/definitions/dimensions"
                                            },
                                            "grid": {
                                                "$ref": "#/definitions/grid"
                                            },
                                            "headline": {
                                                "properties": {
                                                    "color": {
                                                        "type": "string"
                                                    },
                                                    "dimensions": {
                                                        "$ref": "#/definitions/dimensions"
                                                    },
                                                    "fontSize": {
                                                        "type": "number"
                                                    },
                                                    "label": {
                                                        "type": "string"
                                                    },
                                                    "position": {
                                                        "$ref": "#/definitions/position"
                                                    }
                                                },
                                                "required": [
                                                    "dimensions",
                                                    "position",
                                                    "label",
                                                    "color",
                                                    "fontSize"
                                                ],
                                                "type": "object"
                                            },
                                            "labels": {
                                                "items": {
                                                    "properties": {
                                                        "color": {
                                                            "type": "string"
                                                        },
                                                        "dimensions": {
                                                            "$ref": "#/definitions/dimensions"
                                                        },
                                                        "fontSize": {
                                                            "type": "number"
                                                        },
                                                        "label": {
                                                            "type": "string"
                                                        },
                                                        "position": {
                                                            "$ref": "#/definitions/position"
                                                        }
                                                    },
                                                    "required": [
                                                        "dimensions",
                                                        "position",
                                                        "label",
                                                        "color",
                                                        "fontSize"
                                                    ],
                                                    "type": "object"
                                                },
                                                "type": "array"
                                            },
                                            "lineWidth": {
                                                "type": "number"
                                            },
                                            "position": {
                                                "$ref": "#/definitions/position"
                                            },
                                            "subGrid": {
                                                "$ref": "#/definitions/grid"
                                            },
                                            "visible": {
                                                "type": "boolean"
                                            },
                                            "visibleTicks": {
                                                "type": "boolean"
                                            }
                                        },
                                        "required": [
                                            "visible",
                                            "dimensions",
                                            "position"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "visible": {
                                    "type": "boolean"
                                }
                            },
                            "required": [
                                "visible",
                                "dimensions",
                                "preferredSize",
                                "position"
                            ],
                            "type": "object"
                        },
                        {
                            "properties": {
                                "backgroundColor": {
                                    "type": "string"
                                },
                                "dimensions": {
                                    "$ref": "#/definitions/dimensions"
                                },
                                "foregroundColor": {
                                    "type": "string"
                                },
                                "position": {
                                    "$ref": "#/definitions/position"
                                },
                                "tiles": {
                                    "items": {
                                        "properties": {
                                            "dimensions": {
                                                "$ref": "#/definitions/dimensions"
                                            },
                                            "name": {
                                                "type": "string"
                                            },
                                            "position": {
                                                "$ref": "#/definitions/position"
                                            }
                                        },
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "visible": {
                                    "type": "boolean"
                                }
                            },
                            "type": "object"
                        }
                    ]
                },
                "type": "array"
            },
            "dimensions": {
                "$ref": "#/definitions/dimensions"
            },
            "foregroundColor": {
                "type": "string"
            },
            "gradientBackground": {
                "type": "boolean"
            },
            "gradientBackgroundColor": {
                "type": "string"
            },
            "headline": {
                "properties": {
                    "color": {
                        "type": "string"
                    },
                    "dimensions": {
                        "$ref": "#/definitions/dimensions"
                    },
                    "fontSize": {
                        "type": "number"
                    },
                    "label": {
                        "type": "string"
                    },
                    "position": {
                        "$ref": "#/definitions/position"
                    }
                },
                "required": [
                    "dimensions",
                    "position",
                    "label",
                    "color",
                    "fontSize"
                ],
                "type": "object"
            },
            "overview": {
                "$ref": "#/definitions/overview"
            },
            "position": {
                "$ref": "#/definitions/position"
            },
            "showTooltip": {
                "type": "boolean"
            }
        },
        "required": [
            "dimensions",
            "position",
            "backgroundColor",
            "foregroundColor",
            "showTooltip",
            "chartType",
            "charts"
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
            }
        },
        "required": [
            "controlName",
            "scopeConfig"
        ],
        "type": "object"
    }
}
```
