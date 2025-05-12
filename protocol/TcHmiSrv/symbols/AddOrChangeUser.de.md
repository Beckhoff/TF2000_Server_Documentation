# Call an authentication extension's AddUser function and subsequently edit the associated USERGROUPUSERS entry. When the 'parameters' object doesn't exist, this function only edits the USERGROUPUSERS entry.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"AddOrChangeUser"` |
| Kategorie | usersAndSessions |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |  |
| - | - | - |
| domain | string | Domain name of the authentication extension |
| userName | string | Name of the user without domain prefix |
| parameters |  |  |
| settings | object | Changes to the USERGROUPUSERS entry of the user |

## Beispiel-Anfrage - WebSocket

Add a user called 'test' with a specific set of account settings.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "AddOrChangeUser",
            "writeValue": {
                "domain": "TcHmiUserManagement",
                "settings": {
                    "autoLogoff": "P10D",
                    "groups": [
                        "__SystemUsers"
                    ],
                    "locale": "client",
                    "timeFormatLocale": "client",
                    "timezone": "client"
                },
                "userName": "test"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Add a user called 'test' with a specific set of account settings.
```javascript
TcHmi.Server.writeSymbol('AddOrChangeUser',
    {
        "domain": "TcHmiUserManagement",
        "settings": {
            "autoLogoff": "P10D",
            "groups": [
                "__SystemUsers"
            ],
            "locale": "client",
            "timeFormatLocale": "client",
            "timezone": "client"
        },
        "userName": "test"
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
            'AddOrChangeUser=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "function": true,
        "properties": {
            "settings": {
                "properties": {
                    "autoLogoff": {
                        "format": "timespan",
                        "type": "string"
                    },
                    "groups": {
                        "$ref": "tchmi:server#/definitions/userGroups"
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
            }
        },
        "type": "object"
    },
    "writeValue": {
        "properties": {
            "domain": {
                "description": "Domain name of the authentication extension",
                "type": "string"
            },
            "parameters": {
                "anyOf": [
                    {
                        "additionalProperties": true,
                        "description": "Parameters that are forwarded to the authentication extension's AddUser function. Notice that the userName without the domain is forwarded automatically.",
                        "properties": {
                            "password": {
                                "format": "masked",
                                "type": "string"
                            }
                        },
                        "required": [
                            "password"
                        ],
                        "type": "object"
                    },
                    {
                        "$ref": "tchmi:general#/definitions/VOID"
                    }
                ]
            },
            "settings": {
                "additionalProperties": false,
                "description": "Changes to the USERGROUPUSERS entry of the user",
                "properties": {
                    "autoLogoff": {
                        "format": "timespan",
                        "type": "string"
                    },
                    "groups": {
                        "$ref": "tchmi:server#/definitions/userGroups"
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
            "userName": {
                "description": "Name of the user without domain prefix",
                "type": "string"
            }
        },
        "required": [
            "userName",
            "domain"
        ],
        "type": "object"
    }
}
```
