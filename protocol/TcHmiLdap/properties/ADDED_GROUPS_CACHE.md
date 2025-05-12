# This cache is needed to correctly remove user group memberships that were configured based on group mappings.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::ADDED_GROUPS_CACHE"` |
| Category | integration |
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
            "symbol": "TcHmiLdap.Config::ADDED_GROUPS_CACHE"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::ADDED_GROUPS_CACHE', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::ADDED_GROUPS_CACHE=' +
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
        "items": {
            "optionMethod": {
                "symbol": "TcHmiSrv.Config::USERGROUPS"
            },
            "type": "string"
        },
        "type": "array",
        "uniqueItems": true
    },
    "category": "integration",
    "configDescription": "DESC_ADDED_GROUPS_CACHE",
    "propertyOrder": 21,
    "type": "object",
    "visibility": "HideInEngineering"
}
```
