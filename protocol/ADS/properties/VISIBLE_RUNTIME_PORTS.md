# Target systems can have many ADS ports. Most are rarely used in HMI projects.

## General information

|  |  |
| - | - |
| Domain | `"ADS"` |
| Full symbol path | `"ADS.Config::VISIBLE_RUNTIME_PORTS"` |
| Visibility | HideInEngineering |
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
            "symbol": "ADS.Config::VISIBLE_RUNTIME_PORTS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::VISIBLE_RUNTIME_PORTS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::VISIBLE_RUNTIME_PORTS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"array"` |
| Implicit access is allowed | Yes |

## Default value

```json
[
    301,
    302,
    303,
    304,
    350,
    351,
    352,
    353,
    354,
    355,
    501,
    801,
    811,
    821,
    831,
    851,
    852,
    853,
    854,
    10000,
    19800
]
```

## JSON schema

```json
{
    "default": [
        301,
        302,
        303,
        304,
        350,
        351,
        352,
        353,
        354,
        355,
        501,
        801,
        811,
        821,
        831,
        851,
        852,
        853,
        854,
        10000,
        19800
    ],
    "items": {
        "allOf": [
            {
                "$ref": "tchmi:general#/definitions/UINT16"
            },
            {
                "minimum": 1
            }
        ]
    },
    "propertyOrder": 6,
    "type": "array",
    "visibility": "HideInEngineering"
}
```
