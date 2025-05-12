# EtherCAT slave

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "properties": {
        "EtherCAT": {
            "properties": {
                "identity": {
                    "properties": {
                        "addrs": {
                            "properties": {
                                "autoInc": {
                                    "type": "integer"
                                },
                                "phys": {
                                    "type": "integer"
                                }
                            },
                            "required": [
                                "autoInc",
                                "phys"
                            ],
                            "type": "object"
                        },
                        "name": {
                            "type": "string"
                        },
                        "product": {
                            "type": "integer"
                        },
                        "revision": {
                            "type": "integer"
                        },
                        "serial": {
                            "type": "integer"
                        },
                        "type": {
                            "type": "string"
                        },
                        "vendor": {
                            "properties": {
                                "id": {
                                    "type": "integer"
                                },
                                "memberNameLong": {
                                    "type": "string"
                                },
                                "memberNameShort": {
                                    "type": "string"
                                }
                            },
                            "required": [
                                "id",
                                "memberNameLong",
                                "memberNameShort"
                            ],
                            "type": "object"
                        }
                    },
                    "required": [
                        "addrs",
                        "name",
                        "product",
                        "revision",
                        "serial",
                        "type",
                        "vendor"
                    ],
                    "type": "object"
                },
                "syncUnitsAssignment": {
                    "items": [
                        {
                            "type": "integer"
                        }
                    ],
                    "type": "array"
                }
            },
            "required": [
                "identity",
                "syncUnitsAssignment"
            ],
            "type": "object"
        },
        "hotConnect": {
            "properties": {
                "isHotConnectHead": {
                    "type": "boolean"
                },
                "isHotConnectSlave": {
                    "type": "boolean"
                },
                "slaveCountActual": {
                    "type": "integer"
                },
                "slaveCountConfig": {
                    "type": "integer"
                }
            },
            "required": [
                "isHotConnectHead",
                "isHotConnectSlave",
                "slaveCountActual",
                "slaveCountConfig"
            ],
            "type": "object"
        },
        "ports": {
            "items": [
                {
                    "properties": {
                        "autoIncAddr": {
                            "type": "integer"
                        },
                        "configured": {
                            "type": "boolean"
                        },
                        "configuredSlave": {
                            "$ref": "#/definitions/slave"
                        },
                        "physAddr": {
                            "type": "integer"
                        },
                        "physic": {
                            "type": "integer"
                        },
                        "redundancy": {
                            "type": "boolean"
                        },
                        "redundancyPath": {
                            "type": "boolean"
                        }
                    },
                    "required": [
                        "autoIncAddr",
                        "configured",
                        "physAddr",
                        "physic"
                    ],
                    "type": "object"
                }
            ],
            "type": "array"
        },
        "processData": {
            "properties": {
                "in": {
                    "items": [
                        {
                            "properties": {
                                "entries": {
                                    "items": [
                                        {
                                            "properties": {
                                                "bitLength": {
                                                    "type": "integer"
                                                },
                                                "index": {
                                                    "type": "string"
                                                },
                                                "name": {
                                                    "type": "string"
                                                },
                                                "subIndex": {
                                                    "type": "string"
                                                },
                                                "type": {
                                                    "type": "string"
                                                }
                                            },
                                            "required": [
                                                "bitLength",
                                                "index",
                                                "name",
                                                "subIndex",
                                                "type"
                                            ],
                                            "type": "object"
                                        }
                                    ],
                                    "type": "array"
                                },
                                "index": {
                                    "type": "string"
                                },
                                "name": {
                                    "type": "string"
                                }
                            },
                            "required": [
                                "entries",
                                "index",
                                "name"
                            ],
                            "type": "object"
                        }
                    ],
                    "type": "array"
                },
                "out": {
                    "items": [
                        {
                            "properties": {
                                "entries": {
                                    "items": [
                                        {
                                            "properties": {
                                                "bitLength": {
                                                    "type": "integer"
                                                },
                                                "index": {
                                                    "type": "string"
                                                },
                                                "name": {
                                                    "type": "string"
                                                },
                                                "subIndex": {
                                                    "type": "string"
                                                },
                                                "type": {
                                                    "type": "string"
                                                }
                                            },
                                            "required": [
                                                "bitLength",
                                                "index",
                                                "name",
                                                "subIndex",
                                                "type"
                                            ],
                                            "type": "object"
                                        }
                                    ],
                                    "type": "array"
                                },
                                "index": {
                                    "type": "string"
                                },
                                "name": {
                                    "type": "string"
                                }
                            },
                            "required": [
                                "entries",
                                "index",
                                "name"
                            ],
                            "type": "object"
                        }
                    ],
                    "type": "array"
                }
            },
            "required": [
                "in",
                "out"
            ],
            "type": "object"
        }
    },
    "required": [
        "EtherCAT",
        "hotConnect",
        "ports",
        "processData"
    ],
    "type": "object"
}
```
