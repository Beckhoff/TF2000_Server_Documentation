# Allows certain changes to the settings of the current user. Blocked for guest sessions. When the 'password' object exists, the authentication extension's ChangePassword function is called with this object as 'writeValue'.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"ChangeUserSettings"` |
| Category | usersAndSessions |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Change the locale and timezone information of the current user.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ChangeUserSettings",
            "writeValue": {
                "locale": "client",
                "timeFormatLocale": "client",
                "timezone": "client"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Change the locale and timezone information of the current user.
```javascript
TcHmi.Server.writeSymbol('ChangeUserSettings',
    {
        "locale": "client",
        "timeFormatLocale": "client",
        "timezone": "client"
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
            'ChangeUserSettings=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "anyOf": [
            {
                "additionalProperties": false,
                "description": "Changes to the USERGROUPUSERS entry of the current user.",
                "properties": {
                    "changePassword": {
                        "allOf": [
                            {
                                "$ref": "tchmi:general#/definitions/Any"
                            },
                            {
                                "description": "Parameters that are forwarded to the authentication extension's ChangePassword function."
                            }
                        ]
                    },
                    "locale": {
                        "$ref": "tchmi:server#/definitions/userLocale"
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
            {
                "allOf": [
                    {
                        "$ref": "tchmi:general#/definitions/VOID"
                    },
                    {
                        "description": "Calling this method without writeValue will read the current settings."
                    }
                ]
            }
        ]
    }
}
```
