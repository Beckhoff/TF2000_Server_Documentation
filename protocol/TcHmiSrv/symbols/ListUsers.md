# Returns a list of all users and their permissions.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ListUsers"` |
| Visibility | AlwaysShow |

## Version 1.0

Only the 'name', 'domain' and 'groups' are returned.
## Version 2.0

Since version 2.0, the user properties 'locale', 'timeFormatLocale', 'timeZone', and 'autoLogoff' are also returned.
## Sample request - WebSocket

List all users and their permissions.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListUsers"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

List all users and their permissions.
```javascript
TcHmi.Server.readSymbol('ListUsers', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListUsers=' +
        data.response.commands[0].readValue);
});
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "anyOf": [
            {
                "function": true,
                "items": {
                    "description": "List of all users and their permissions.",
                    "properties": {
                        "domain": {
                            "type": "string"
                        },
                        "groups": {
                            "items": {
                                "type": "string"
                            },
                            "type": "array"
                        },
                        "name": {
                            "type": "string"
                        }
                    },
                    "type": "object"
                },
                "type": "array",
                "versions": [
                    1.0
                ]
            },
            {
                "function": true,
                "items": {
                    "description": "List of all users and their permissions.",
                    "properties": {
                        "autoLogoff": {
                            "format": "timespan",
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
                            "$ref": "tchmi:server#/definitions/userLocale"
                        },
                        "name": {
                            "type": "string"
                        },
                        "timeFormatLocale": {
                            "$ref": "tchmi:server#/definitions/userLocale"
                        },
                        "timeZone": {
                            "$ref": "tchmi:server#/definitions/userTimeZone"
                        }
                    },
                    "type": "object"
                },
                "type": "array",
                "versions": [
                    2.0
                ]
            }
        ]
    },
    "versions": {
        "1.0": {
            "description": "Only the 'name', 'domain' and 'groups' are returned."
        },
        "2.0": {
            "description": "Since version 2.0, the user properties 'locale', 'timeFormatLocale', 'timeZone', and 'autoLogoff' are also returned."
        }
    }
}
```
