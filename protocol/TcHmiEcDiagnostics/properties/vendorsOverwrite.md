# Add vendor ID

## General information

|  |  |
| - | - |
| Domain | `"TcHmiEcDiagnostics"` |
| Full symbol path | `"TcHmiEcDiagnostics.Config::vendorsOverwrite"` |
| Visibility | AlwaysShow |
| Contained in every configuration by default | No |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiEcDiagnostics.Config::vendorsOverwrite"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiEcDiagnostics.Config::vendorsOverwrite', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiEcDiagnostics.Config::vendorsOverwrite=' +
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
    "1": {
        "longName": "EtherCAT Technology Group",
        "shortName": "ETG"
    },
    "2": {
        "longName": "Beckhoff Automation GmbH & Co. KG",
        "shortName": "Beckhoff"
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "properties": {
            "devices": {
                "items": {
                    "additionalProperties": false,
                    "properties": {
                        "longName": {
                            "type": "string"
                        },
                        "pattern": {
                            "type": "string"
                        },
                        "shortName": {
                            "type": "string"
                        }
                    },
                    "required": [
                        "pattern"
                    ],
                    "type": "object"
                },
                "type": "array"
            },
            "longName": {
                "type": "string"
            },
            "shortName": {
                "type": "string"
            }
        },
        "required": [
            "devices"
        ],
        "type": "object"
    },
    "default": {
        "1": {
            "longName": "EtherCAT Technology Group",
            "shortName": "ETG"
        },
        "2": {
            "longName": "Beckhoff Automation GmbH & Co. KG",
            "shortName": "Beckhoff"
        }
    },
    "type": "object"
}
```
