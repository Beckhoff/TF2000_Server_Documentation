# Get online information from the slaves of a specific EtherCAT master.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiEcDiagnostics.GetSlavesOnlineInfo"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get online information from the slaves of the 'Device1' EtherCAT master.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.GetSlavesOnlineInfo",
            "writeValue": "Device1"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get online information from the slaves of the 'Device1' EtherCAT master.
```javascript
TcHmi.Server.writeSymbol('TcHmiEcDiagnostics.GetSlavesOnlineInfo',
    "Device1",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiEcDiagnostics.GetSlavesOnlineInfo=' +
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
            "config": {
                "properties": {
                    "masterNetId": {
                        "type": "string"
                    },
                    "targetNetId": {
                        "type": "string"
                    }
                },
                "type": "object"
            },
            "slaves": {
                "properties": {
                    "1001": {
                        "properties": {
                            "counter": {
                                "properties": {
                                    "abnormalChanges": {
                                        "type": "integer"
                                    },
                                    "connectionLosses": {
                                        "type": "integer"
                                    }
                                },
                                "required": [
                                    "abnormalChanges",
                                    "connectionLosses"
                                ],
                                "type": "object"
                            },
                            "current": {
                                "properties": {
                                    "disabled": {
                                        "type": "boolean"
                                    },
                                    "identity": {
                                        "properties": {
                                            "isInvalid": {
                                                "type": "boolean"
                                            },
                                            "isInvalidOnPrevSlaves": {
                                                "type": "integer"
                                            }
                                        },
                                        "required": [
                                            "isInvalid",
                                            "isInvalidOnPrevSlaves"
                                        ],
                                        "type": "object"
                                    },
                                    "initError": {
                                        "type": "boolean"
                                    },
                                    "presence": {
                                        "properties": {
                                            "notPresent": {
                                                "type": "boolean"
                                            },
                                            "notPresentOnPrevSlaves": {
                                                "type": "integer"
                                            }
                                        },
                                        "required": [
                                            "notPresent",
                                            "notPresentOnPrevSlaves"
                                        ],
                                        "type": "object"
                                    },
                                    "signalsError": {
                                        "type": "boolean"
                                    },
                                    "stateMachine": {
                                        "type": "integer"
                                    }
                                },
                                "required": [
                                    "disabled",
                                    "identity",
                                    "initError",
                                    "presence",
                                    "signalsError",
                                    "stateMachine"
                                ],
                                "type": "object"
                            },
                            "ports": {
                                "items": [
                                    {
                                        "properties": {
                                            "counter": {
                                                "properties": {
                                                    "crc": {
                                                        "properties": {
                                                            "errorOnPrevPort": {
                                                                "type": "boolean"
                                                            },
                                                            "total": {
                                                                "type": "integer"
                                                            }
                                                        },
                                                        "required": [
                                                            "errorOnPrevPort",
                                                            "total"
                                                        ],
                                                        "type": "object"
                                                    }
                                                },
                                                "required": [
                                                    "crc"
                                                ],
                                                "type": "object"
                                            },
                                            "current": {
                                                "properties": {
                                                    "linkError": {
                                                        "type": "boolean"
                                                    },
                                                    "missingLink": {
                                                        "type": "boolean"
                                                    },
                                                    "unexpectedLink": {
                                                        "type": "boolean"
                                                    }
                                                },
                                                "required": [
                                                    "linkError",
                                                    "missingLink",
                                                    "unexpectedLink"
                                                ],
                                                "type": "object"
                                            }
                                        },
                                        "required": [
                                            "counter",
                                            "current"
                                        ],
                                        "type": "object"
                                    },
                                    {
                                        "properties": {
                                            "counter": {
                                                "properties": {
                                                    "crc": {
                                                        "properties": {
                                                            "errorOnPrevPort": {
                                                                "type": "boolean"
                                                            },
                                                            "total": {
                                                                "type": "integer"
                                                            }
                                                        },
                                                        "required": [
                                                            "errorOnPrevPort",
                                                            "total"
                                                        ],
                                                        "type": "object"
                                                    }
                                                },
                                                "required": [
                                                    "crc"
                                                ],
                                                "type": "object"
                                            },
                                            "current": {
                                                "properties": {
                                                    "linkError": {
                                                        "type": "boolean"
                                                    },
                                                    "missingLink": {
                                                        "type": "boolean"
                                                    },
                                                    "unexpectedLink": {
                                                        "type": "boolean"
                                                    }
                                                },
                                                "required": [
                                                    "linkError",
                                                    "missingLink",
                                                    "unexpectedLink"
                                                ],
                                                "type": "object"
                                            }
                                        },
                                        "required": [
                                            "counter",
                                            "current"
                                        ],
                                        "type": "object"
                                    },
                                    {
                                        "properties": {
                                            "counter": {
                                                "properties": {
                                                    "crc": {
                                                        "properties": {
                                                            "errorOnPrevPort": {
                                                                "type": "boolean"
                                                            },
                                                            "total": {
                                                                "type": "integer"
                                                            }
                                                        },
                                                        "required": [
                                                            "errorOnPrevPort",
                                                            "total"
                                                        ],
                                                        "type": "object"
                                                    }
                                                },
                                                "required": [
                                                    "crc"
                                                ],
                                                "type": "object"
                                            },
                                            "current": {
                                                "properties": {
                                                    "linkError": {
                                                        "type": "boolean"
                                                    },
                                                    "missingLink": {
                                                        "type": "boolean"
                                                    },
                                                    "unexpectedLink": {
                                                        "type": "boolean"
                                                    }
                                                },
                                                "required": [
                                                    "linkError",
                                                    "missingLink",
                                                    "unexpectedLink"
                                                ],
                                                "type": "object"
                                            }
                                        },
                                        "required": [
                                            "counter",
                                            "current"
                                        ],
                                        "type": "object"
                                    },
                                    {
                                        "properties": {
                                            "counter": {
                                                "properties": {
                                                    "crc": {
                                                        "properties": {
                                                            "errorOnPrevPort": {
                                                                "type": "boolean"
                                                            },
                                                            "total": {
                                                                "type": "integer"
                                                            }
                                                        },
                                                        "required": [
                                                            "errorOnPrevPort",
                                                            "total"
                                                        ],
                                                        "type": "object"
                                                    }
                                                },
                                                "required": [
                                                    "crc"
                                                ],
                                                "type": "object"
                                            },
                                            "current": {
                                                "properties": {
                                                    "linkError": {
                                                        "type": "boolean"
                                                    },
                                                    "missingLink": {
                                                        "type": "boolean"
                                                    },
                                                    "unexpectedLink": {
                                                        "type": "boolean"
                                                    }
                                                },
                                                "required": [
                                                    "linkError",
                                                    "missingLink",
                                                    "unexpectedLink"
                                                ],
                                                "type": "object"
                                            }
                                        },
                                        "required": [
                                            "counter",
                                            "current"
                                        ],
                                        "type": "object"
                                    }
                                ],
                                "type": "array"
                            },
                            "requested": {
                                "properties": {
                                    "stateMachine": {
                                        "type": "integer"
                                    }
                                },
                                "required": [
                                    "stateMachine"
                                ],
                                "type": "object"
                            },
                            "syncUnits": {
                                "properties": {
                                    "0": {
                                        "properties": {
                                            "error": {
                                                "type": "boolean"
                                            },
                                            "frameMissedCounter": {
                                                "type": "integer"
                                            },
                                            "wcFaultCounter": {
                                                "type": "integer"
                                            }
                                        },
                                        "required": [
                                            "error",
                                            "frameMissedCounter",
                                            "wcFaultCounter"
                                        ],
                                        "type": "object"
                                    }
                                },
                                "required": [
                                    "0"
                                ],
                                "type": "object"
                            }
                        },
                        "required": [
                            "counter",
                            "current",
                            "ports",
                            "requested",
                            "syncUnits"
                        ],
                        "type": "object"
                    }
                },
                "type": "object"
            }
        },
        "required": [
            "config",
            "slaves"
        ],
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "type": "string"
    }
}
```
