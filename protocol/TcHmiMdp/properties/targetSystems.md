# Target systems from which data can be queried.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiMdp"` |
| Full symbol path | `"TcHmiMdp.Config::targetSystems"` |
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
            "symbol": "TcHmiMdp.Config::targetSystems"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiMdp.Config::targetSystems', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiMdp.Config::targetSystems=' +
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
    "Local": {
        "address": "127.0.0.1.1.1"
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "configDescription": "descTargetSystem",
        "properties": {
            "address": {
                "$ref": "tchmi:server#/definitions/adsRoute"
            },
            "enabled": {
                "default": true,
                "type": "boolean"
            },
            "readOnly": {
                "configDescription": "descReadOnly",
                "default": false,
                "type": "boolean"
            }
        },
        "required": [
            "address",
            "enabled",
            "readOnly"
        ],
        "type": "object"
    },
    "configDescription": "descTargetSystems",
    "default": {
        "Local": {
            "address": "127.0.0.1.1.1"
        }
    },
    "defaultConfigurable": true,
    "type": "object"
}
```
