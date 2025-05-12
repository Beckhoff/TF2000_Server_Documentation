# Return the currently active user.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"GetCurrentUser"` |
| Category | usersAndSessions |
| Visibility | AlwaysShow |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "GetCurrentUser"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('GetCurrentUser', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'GetCurrentUser=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true,
        "properties": {
            "autoLoginUser": {
                "type": "boolean"
            },
            "autoLogoff": {
                "format": "timespan",
                "type": "string"
            },
            "clientCertificate": {
                "type": "string"
            },
            "clientIp": {
                "type": "string"
            },
            "configLocale": {
                "type": "string"
            },
            "configTimeFormatLocale": {
                "type": "string"
            },
            "configTimeZone": {
                "type": "string"
            },
            "domain": {
                "type": "string"
            },
            "groups": {
                "items": {
                    "type": "string"
                },
                "type": "array"
            },
            "locale": {
                "type": "string"
            },
            "name": {
                "type": "string"
            },
            "session": {
                "type": "string"
            },
            "timeFormatLocale": {
                "type": "string"
            },
            "timeZone": {
                "type": "string"
            }
        },
        "type": "object"
    }
}
```
