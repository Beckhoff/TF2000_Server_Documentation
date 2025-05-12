# Get information about the connection between the HMI server and the configured LDAP server.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Diagnostics"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

LDAP connectionState Subscription
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiLdap.Diagnostics::connectionState"
        }
    ],
    "requestType": "Subscription"
}
```

## Sample request - JavaScript

LDAP connectionState Subscription
```javascript
TcHmi.Server.request('TcHmiLdap.Diagnostics::connectionState',
    {
        "commands": [
            {
                "commandOptions": [
                    "SendErrorMessage",
                    "SendWriteValue"
                ],
                "symbol": "TcHmiLdap.Diagnostics::connectionState"
            }
        ],
        "requestType": "Subscription"
    },
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiLdap.Diagnostics=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "anonBindSucceeded": {
                "propertyOrder": 4,
                "type": "boolean"
            },
            "bindUserBindSucceeded": {
                "propertyOrder": 5,
                "type": "boolean"
            },
            "connectionState": {
                "enum": [
                    "Good",
                    "Not Connected",
                    "Timeout",
                    "Internal Error"
                ],
                "propertyOrder": 1,
                "type": "string"
            },
            "ldapErrorCode": {
                "propertyOrder": 6,
                "type": "integer"
            },
            "sinceLastStateCheck": {
                "format": "timespan",
                "propertyOrder": 2,
                "type": "string",
                "visibility": "HideInEngineering"
            },
            "tcpConnectionEstablished": {
                "propertyOrder": 3,
                "type": "boolean"
            }
        },
        "required": [
            "connectionState"
        ],
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ]
}
```
