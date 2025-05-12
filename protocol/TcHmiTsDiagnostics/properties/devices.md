# EtherCAT devices

## General information

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Full symbol path | `"TcHmiTsDiagnostics.Config::devices"` |
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
            "symbol": "TcHmiTsDiagnostics.Config::devices"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiTsDiagnostics.Config::devices', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiTsDiagnostics.Config::devices=' +
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
    "Device1": {
        "enabled": true,
        "masterNetId": "0.0.0.0.2.1",
        "targetNetId": "0.0.0.0.1.1"
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "properties": {
            "enabled": {
                "default": true,
                "propertyOrder": 1,
                "type": "boolean"
            },
            "masterNetId": {
                "format": "amsnetid",
                "optionMethod": {
                    "symbol": "TcHmiTsDiagnostics.ListMastersOfRoute",
                    "writeValue": {
                        "$data": "#/properties/devices/additionalProperties/targetNetId"
                    }
                },
                "propertyOrder": 3,
                "type": "string"
            },
            "safetyProjects": {
                "additionalProperties": {
                    "keyOptionMethod": {
                        "symbol": "TcHmiTsDiagnostics.ProjectNameSuggestions"
                    },
                    "properties": {
                        "targetSystemAmsPort": {
                            "default": 1001,
                            "description": "The AmsPort of the Target System.",
                            "propertyOrder": 2,
                            "type": "integer"
                        },
                        "xmlFile": {
                            "acceptFileTypes": [
                                ".xml"
                            ],
                            "default": "",
                            "format": "base64",
                            "propertyOrder": 1,
                            "type": "string"
                        }
                    },
                    "required": [
                        "xmlFile",
                        "targetSystemAmsPort"
                    ],
                    "type": "object"
                },
                "description": "xmlFiles",
                "propertyOrder": 4,
                "type": "object"
            },
            "targetNetId": {
                "format": "amsnetid",
                "optionMethod": {
                    "symbol": "ADS.ListRoutes"
                },
                "propertyOrder": 2,
                "type": "string"
            }
        },
        "required": [
            "enabled",
            "targetNetId",
            "masterNetId",
            "safetyProjects"
        ],
        "type": "object"
    },
    "default": {
        "Device1": {
            "enabled": true,
            "masterNetId": "0.0.0.0.2.1",
            "targetNetId": "0.0.0.0.1.1"
        }
    },
    "defaultConfigurable": true,
    "type": "object"
}
```
