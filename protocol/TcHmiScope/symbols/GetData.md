# Get Data for a specific ScopeChart. Symbols must be called from the same socket as OpenConnection.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Full symbol path | `"TcHmiScope.GetData"` |
| Visibility | AlwaysShow |

## Parameters

|  |  |  |
| - | - | - |
| controlName | string | ScopeChart Name. |
| scopeConfig | object | Information for scope config. |

## Sample request - WebSocket

Get Data for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiScope.GetData",
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

## Sample request - JavaScript

Get Data for ScopeChart named 'MyScopeYT Chart'. Symbols must be called from the same socket as OpenConnection.
```javascript
TcHmi.Server.writeSymbol('TcHmiScope.GetData',
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
            'TcHmiScope.GetData=' +
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
            "charts": {
                "items": {
                    "oneOf": [
                        {
                            "properties": {
                                "graphs": {
                                    "additionalProperties": {
                                        "properties": {
                                            "axesData": {
                                                "items": {
                                                    "properties": {
                                                        "x": {
                                                            "format": "date-time",
                                                            "type": "string"
                                                        },
                                                        "y": {
                                                            "type": "number"
                                                        }
                                                    },
                                                    "type": "object"
                                                },
                                                "type": "array"
                                            },
                                            "lineSeries": {
                                                "items": {
                                                    "properties": {
                                                        "index": {
                                                            "type": "number"
                                                        },
                                                        "lineStates": {
                                                            "items": {
                                                                "type": [
                                                                    "number"
                                                                ]
                                                            },
                                                            "type": "array"
                                                        }
                                                    },
                                                    "type": "object"
                                                },
                                                "type": "array"
                                            },
                                            "tooltipDelta": {
                                                "type": "number"
                                            },
                                            "zeroPoint": {
                                                "$ref": "#/definitions/position"
                                            }
                                        },
                                        "required": [
                                            "axesData",
                                            "zeroPoint",
                                            "tooltipDelta"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "object"
                                },
                                "trigger": {
                                    "items": {
                                        "properties": {
                                            "color": {
                                                "type": "string"
                                            },
                                            "dimensions": {
                                                "$ref": "#/definitions/dimensions"
                                            },
                                            "icon": {
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
                                            "id": {
                                                "type": "number"
                                            },
                                            "label": {
                                                "properties": {
                                                    "color": {
                                                        "type": "string"
                                                    },
                                                    "fontSize": {
                                                        "type": "number"
                                                    },
                                                    "label": {
                                                        "type": "string"
                                                    },
                                                    "position": {
                                                        "enum": [
                                                            "Right",
                                                            "Left"
                                                        ],
                                                        "type": "string"
                                                    }
                                                },
                                                "required": [
                                                    "dimensions",
                                                    "position",
                                                    "color",
                                                    "label"
                                                ],
                                                "type": "object"
                                            },
                                            "lineWidth": {
                                                "type": "number"
                                            },
                                            "orientation": {
                                                "type": "string"
                                            },
                                            "position": {
                                                "$ref": "#/definitions/position"
                                            },
                                            "text": {
                                                "properties": {
                                                    "backgroundColor": {
                                                        "type": "string"
                                                    },
                                                    "color": {
                                                        "type": "string"
                                                    },
                                                    "dimensions": {
                                                        "$ref": "#/definitions/dimensions"
                                                    },
                                                    "fontSize": {
                                                        "type": "number"
                                                    },
                                                    "position": {
                                                        "$ref": "#/definitions/position"
                                                    },
                                                    "text": {
                                                        "type": "string"
                                                    }
                                                },
                                                "required": [
                                                    "dimensions",
                                                    "position",
                                                    "color",
                                                    "backgroundColor"
                                                ],
                                                "type": "object"
                                            }
                                        },
                                        "required": [
                                            "id",
                                            "color",
                                            "lineWidth",
                                            "orientation",
                                            "dimensions",
                                            "position"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "xyTrigger": {
                                    "items": {
                                        "properties": {
                                            "circle": {
                                                "properties": {
                                                    "diameter": {
                                                        "type": "number"
                                                    },
                                                    "middlePoint": {
                                                        "$ref": "#/definitions/position"
                                                    }
                                                },
                                                "type": "object"
                                            },
                                            "color": {
                                                "type": "string"
                                            },
                                            "id": {
                                                "type": "number"
                                            },
                                            "lineWidth": {
                                                "type": "number"
                                            },
                                            "marker": {
                                                "properties": {
                                                    "horizontal": {
                                                        "properties": {
                                                            "point1": {
                                                                "$ref": "#/definitions/position"
                                                            },
                                                            "point2": {
                                                                "$ref": "#/definitions/position"
                                                            }
                                                        },
                                                        "type": "object"
                                                    },
                                                    "vertical": {
                                                        "properties": {
                                                            "point1": {
                                                                "$ref": "#/definitions/position"
                                                            },
                                                            "point2": {
                                                                "$ref": "#/definitions/position"
                                                            }
                                                        },
                                                        "type": "object"
                                                    }
                                                },
                                                "type": "object"
                                            }
                                        },
                                        "required": [
                                            "id"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "array"
                                }
                            },
                            "required": [
                                "graphs"
                            ],
                            "type": "object"
                        },
                        {
                            "properties": {
                                "tiles": {
                                    "items": {
                                        "properties": {
                                            "digitalView": {
                                                "properties": {
                                                    "digits": {
                                                        "items": {
                                                            "properties": {
                                                                "bottom": {
                                                                    "$ref": "#/definitions/fullPolygon"
                                                                },
                                                                "bottomLeft": {
                                                                    "$ref": "#/definitions/fullPolygon"
                                                                },
                                                                "bottomRight": {
                                                                    "$ref": "#/definitions/fullPolygon"
                                                                },
                                                                "middle": {
                                                                    "$ref": "#/definitions/fullPolygon"
                                                                },
                                                                "top": {
                                                                    "$ref": "#/definitions/fullPolygon"
                                                                },
                                                                "topLeft": {
                                                                    "$ref": "#/definitions/fullPolygon"
                                                                },
                                                                "topRight": {
                                                                    "$ref": "#/definitions/fullPolygon"
                                                                }
                                                            },
                                                            "type": "object"
                                                        },
                                                        "type": "array"
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
                                                                "name": {
                                                                    "type": "string"
                                                                },
                                                                "position": {
                                                                    "$ref": "#/definitions/position"
                                                                },
                                                                "visible": {
                                                                    "type": "boolean"
                                                                }
                                                            },
                                                            "type": "object"
                                                        },
                                                        "type": "array"
                                                    },
                                                    "minus": {
                                                        "$ref": "#/definitions/fullPolygon"
                                                    },
                                                    "separator": {
                                                        "properties": {
                                                            "color": {
                                                                "type": "string"
                                                            },
                                                            "polygon": {
                                                                "$ref": "#/definitions/polygon"
                                                            },
                                                            "seperatorType": {
                                                                "enum": [
                                                                    "dot",
                                                                    "comma"
                                                                ],
                                                                "type": "string"
                                                            }
                                                        },
                                                        "type": "object"
                                                    }
                                                },
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
                                                        "name": {
                                                            "type": "string"
                                                        },
                                                        "position": {
                                                            "$ref": "#/definitions/position"
                                                        },
                                                        "value": {
                                                            "type": "string"
                                                        },
                                                        "visible": {
                                                            "type": "boolean"
                                                        }
                                                    },
                                                    "type": "object"
                                                },
                                                "type": "array"
                                            }
                                        },
                                        "required": [
                                            "digits"
                                        ],
                                        "type": "object"
                                    },
                                    "type": "array"
                                }
                            },
                            "type": "object"
                        }
                    ]
                },
                "type": "array"
            },
            "overview": {
                "properties": {
                    "graphs": {
                        "additionalProperties": {
                            "properties": {
                                "axesData": {
                                    "items": {
                                        "properties": {
                                            "x": {
                                                "format": "date-time",
                                                "type": "string"
                                            },
                                            "y": {
                                                "type": "number"
                                            }
                                        },
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "lineSeries": {
                                    "items": {
                                        "properties": {
                                            "index": {
                                                "type": "number"
                                            },
                                            "lineStates": {
                                                "items": {
                                                    "type": [
                                                        "number"
                                                    ]
                                                },
                                                "type": "array"
                                            }
                                        },
                                        "type": "object"
                                    },
                                    "type": "array"
                                },
                                "tooltipDelta": {
                                    "type": "number"
                                },
                                "zeroPoint": {
                                    "$ref": "#/definitions/position"
                                }
                            },
                            "required": [
                                "axesData",
                                "zeroPoint",
                                "tooltipDelta"
                            ],
                            "type": "object"
                        },
                        "type": "object"
                    },
                    "trigger": {
                        "items": {
                            "properties": {
                                "color": {
                                    "type": "string"
                                },
                                "delta": {
                                    "type": "number"
                                },
                                "dimensions": {
                                    "$ref": "#/definitions/dimensions"
                                },
                                "group": {
                                    "type": "string"
                                },
                                "icon": {
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
                                "id": {
                                    "type": "number"
                                },
                                "label": {
                                    "properties": {
                                        "color": {
                                            "type": "string"
                                        },
                                        "fontSize": {
                                            "type": "number"
                                        },
                                        "label": {
                                            "type": "string"
                                        },
                                        "position": {
                                            "enum": [
                                                "Right",
                                                "Left"
                                            ],
                                            "type": "string"
                                        }
                                    },
                                    "required": [
                                        "dimensions",
                                        "position",
                                        "color",
                                        "label"
                                    ],
                                    "type": "object"
                                },
                                "lineWidth": {
                                    "type": "number"
                                },
                                "locked": {
                                    "type": "boolean"
                                },
                                "orientation": {
                                    "type": "string"
                                },
                                "position": {
                                    "$ref": "#/definitions/position"
                                },
                                "text": {
                                    "properties": {
                                        "backgroundColor": {
                                            "type": "string"
                                        },
                                        "color": {
                                            "type": "string"
                                        },
                                        "dimensions": {
                                            "$ref": "#/definitions/dimensions"
                                        },
                                        "fontSize": {
                                            "type": "number"
                                        },
                                        "position": {
                                            "$ref": "#/definitions/position"
                                        },
                                        "text": {
                                            "type": "string"
                                        }
                                    },
                                    "required": [
                                        "dimensions",
                                        "position",
                                        "color",
                                        "backgroundColor"
                                    ],
                                    "type": "object"
                                }
                            },
                            "required": [
                                "id",
                                "color",
                                "lineWidth",
                                "orientation",
                                "dimensions",
                                "position"
                            ],
                            "type": "object"
                        },
                        "type": "array"
                    }
                },
                "required": [
                    "graphs"
                ],
                "type": "object"
            }
        },
        "required": [
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
