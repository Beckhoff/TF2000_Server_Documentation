# Runtimes

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSystemEngineering"` |
| Full symbol path | `"TcHmiSystemEngineering.Config::runtimes"` |
| Visibility | AlwaysShow |
| Contained in every configuration by default | Yes |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSystemEngineering.Config::runtimes"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSystemEngineering.Config::runtimes', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSystemEngineering.Config::runtimes=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## Default value

```json
{
    "Runtime1": {
        "adsRuntime": "PLC1",
        "autoSymbolUpdate": false,
        "enableAuditTrail": false,
        "enabled": false
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "default": {
            "adsRuntime": "PLC1",
            "autoSymbolUpdate": false,
            "enableAuditTrail": false,
            "enabled": false
        },
        "properties": {
            "adsRuntime": {
                "optionMethod": {
                    "symbol": "ADS.Config::RUNTIMES::{key}"
                },
                "type": "string"
            },
            "autoSymbolUpdate": {
                "description": "autoSymbolUpdate_description",
                "type": "boolean"
            },
            "enableAuditTrail": {
                "description": "enableAuditTrail_description",
                "type": "boolean"
            },
            "enabled": {
                "default": false,
                "type": "boolean"
            },
            "entryPath": {
                "optionMethod": {
                    "symbol": "{domain}.ListSymbolsOfPath",
                    "writeValue": {
                        "adsRuntime": {
                            "$data": "#/properties/runtimes/additionalProperties/adsRuntime"
                        },
                        "path": {
                            "$data": "#/properties/runtimes/additionalProperties/entryPath"
                        }
                    }
                },
                "type": "string"
            },
            "isInitializedSymbol": {
                "optionMethod": {
                    "symbol": "{domain}.ListSymbolsOfPath",
                    "writeValue": {
                        "adsRuntime": {
                            "$data": "#/properties/runtimes/additionalProperties/adsRuntime"
                        },
                        "path": {
                            "$data": "#/properties/runtimes/additionalProperties/isInitializedSymbol"
                        }
                    }
                },
                "type": "string"
            },
            "schema": {
                "properties": {
                    "definitions": {
                        "additionalProperties": true,
                        "type": "object"
                    },
                    "properties": {
                        "additionalProperties": true,
                        "type": "object"
                    },
                    "type": {
                        "type": "string"
                    }
                },
                "type": "object",
                "visibility": "AlwaysHide"
            },
            "schemaHash": {
                "type": "string",
                "visibility": "AlwaysHide"
            },
            "symbolValues": {
                "additionalProperties": {
                    "properties": {
                        "timestamp": {
                            "type": "string"
                        },
                        "value": {}
                    },
                    "required": [
                        "timestamp",
                        "value"
                    ],
                    "type": "object"
                },
                "type": "object",
                "visibility": "AlwaysHide"
            }
        },
        "required": [
            "enabled",
            "adsRuntime",
            "autoSymbolUpdate",
            "enableAuditTrail"
        ],
        "type": "object"
    },
    "default": {
        "Runtime1": {
            "adsRuntime": "PLC1",
            "autoSymbolUpdate": false,
            "enableAuditTrail": false,
            "enabled": false
        }
    },
    "defaultConfigurable": true,
    "type": "object"
}
```
