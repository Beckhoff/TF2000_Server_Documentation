# overview

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "properties": {
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
                    "graphName": {
                        "type": "string"
                    },
                    "graphType": {
                        "type": "string"
                    },
                    "lineColor": {
                        "type": "string"
                    },
                    "lineWidth": {
                        "type": "string"
                    },
                    "markColor": {
                        "type": "string"
                    },
                    "markWidth": {
                        "type": "number"
                    },
                    "marks": {
                        "type": "boolean"
                    }
                },
                "required": [
                    "graphType",
                    "marks",
                    "lineColor",
                    "lineWidth",
                    "lineStyle",
                    "markColor",
                    "markWidth"
                ],
                "type": "object"
            },
            "type": "array"
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
                        "properties": {
                            "color": {
                                "type": "string"
                            },
                            "lineWidth": {
                                "type": "number"
                            },
                            "ticks": {
                                "type": "number"
                            }
                        },
                        "required": [
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
                                "type": "number"
                            }
                        },
                        "required": [
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
}
```
