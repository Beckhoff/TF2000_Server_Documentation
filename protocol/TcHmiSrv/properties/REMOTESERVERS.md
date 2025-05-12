# Connections to other HMI servers. The mapped symbols of remote servers can be used like symbols from extensions of the current server.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::REMOTESERVERS"` |
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
            "symbol": "TcHmiSrv.Config::REMOTESERVERS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::REMOTESERVERS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::REMOTESERVERS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "properties": {
            "REMOTE_CONNECT_TIMEOUT": {
                "default": "PT5S",
                "format": "timespan",
                "type": "string"
            },
            "REMOTE_ENABLED": {
                "default": true,
                "type": "boolean"
            },
            "REMOTE_PASSWORD": {
                "default": "",
                "format": "masked",
                "propertyOrder": 3,
                "type": "string"
            },
            "REMOTE_URL": {
                "propertyOrder": 1,
                "type": "string"
            },
            "REMOTE_USERNAME": {
                "configDescription": "DESC_REMOTE_USERNAME",
                "default": "",
                "propertyOrder": 2,
                "type": "string"
            }
        },
        "required": [
            "REMOTE_ENABLED",
            "REMOTE_URL",
            "REMOTE_USERNAME",
            "REMOTE_PASSWORD",
            "REMOTE_CONNECT_TIMEOUT"
        ],
        "title": "REMOTESERVERS_TITLE",
        "type": "object"
    },
    "configDescription": "DESC_REMOTESERVERS",
    "type": "object"
}
```
