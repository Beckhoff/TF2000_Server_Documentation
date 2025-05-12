# User groups have access permissions to specific symbols and files. Permissions are assigned to users based on user groups they are a member of.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::USERGROUPS"` |
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
            "symbol": "TcHmiSrv.Config::USERGROUPS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::USERGROUPS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::USERGROUPS=' +
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
    "__SystemAdministrators": {
        "ENABLED": true,
        "FILEACCESS": 3,
        "SYMBOLACCESS": 3
    },
    "__SystemGuests": {
        "ENABLED": true,
        "FILEACCESS": 0,
        "FILES": {
            "/Config/ServerState": 1,
            "/FavIcon.ico": 1
        },
        "SYMBOLACCESS": 0,
        "SYMBOLS": {
            "DefaultAuthExtension": 1,
            "DefaultUserGroup": 1,
            "GetCurrentUser": 3,
            "GetSymbolAccess": 3,
            "Heartbeat": 3,
            "IsAuthRequired": 3,
            "ListDomains": 3,
            "ListUserNames": 3,
            "Login": 3,
            "Logout": 3,
            "SetLocale": 3,
            "Unsubscribe": 3,
            "UserSelectType": 1
        }
    },
    "__SystemMaintenanceUsers": {
        "ENABLED": true,
        "SYMBOLACCESS": 0
    },
    "__SystemUsers": {
        "ENABLED": true,
        "FILEACCESS": 3,
        "FILES": {
            "/Config": 1
        },
        "SYMBOLACCESS": 0,
        "SYMBOLS": {
            "ChangeUserSettings": 3,
            "ConfirmAlarm": 3,
            "CreateEvent": 3,
            "DefaultAuthExtension": 1,
            "DefaultUserGroup": 1,
            "Diagnostics": 3,
            "Export": 3,
            "GetConfiguration": 3,
            "GetCurrentUser": 3,
            "GetDefinitions": 3,
            "GetFileInformation": 3,
            "GetSchema": 3,
            "GetServerInformation": 3,
            "GetSymbolAccess": 3,
            "Heartbeat": 3,
            "IsAuthRequired": 3,
            "ListDomains": 3,
            "ListEvents": 3,
            "ListSymbols": 3,
            "ListUserNames": 3,
            "LocalizeText": 3,
            "Login": 3,
            "Logout": 3,
            "SetLocale": 3,
            "SubscribeEvents": 3,
            "TcHmiUserManagement.GetComplexityRules": 3,
            "Unsubscribe": 3,
            "UnsubscribeEvents": 3,
            "UpdateEventsSubscription": 3,
            "UserSelectType": 1
        }
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "configDescription": "DESC_USERGROUP",
        "properties": {
            "ENABLED": {
                "default": true,
                "type": "boolean"
            },
            "FILEACCESS": {
                "$ref": "tchmi:server#/definitions/accessEnum"
            },
            "FILES": {
                "additionalProperties": {
                    "allOf": [
                        {
                            "$ref": "tchmi:server#/definitions/accessEnum"
                        },
                        {
                            "configDescription": "DESC_FILE"
                        }
                    ]
                },
                "type": "object"
            },
            "SYMBOLACCESS": {
                "allOf": [
                    {
                        "$ref": "tchmi:server#/definitions/accessEnum"
                    },
                    {
                        "configDescription": "DESC_SYMBOLACCESS"
                    },
                    {
                        "default": 0
                    }
                ]
            },
            "SYMBOLS": {
                "additionalProperties": {
                    "allOf": [
                        {
                            "$ref": "tchmi:server#/definitions/accessEnum"
                        },
                        {
                            "configDescription": "DESC_SYMBOL"
                        },
                        {
                            "keyOptionMethod": {
                                "symbol": "ListSymbolNames"
                            }
                        }
                    ]
                },
                "configDescription": "DESC_USERGROUPS_SYMBOLS",
                "type": "object"
            }
        },
        "required": [
            "ENABLED",
            "SYMBOLACCESS",
            "FILEACCESS",
            "SYMBOLS",
            "FILES"
        ],
        "type": "object"
    },
    "default": {
        "__SystemAdministrators": {
            "ENABLED": true,
            "FILEACCESS": 3,
            "SYMBOLACCESS": 3
        },
        "__SystemGuests": {
            "ENABLED": true,
            "FILEACCESS": 0,
            "FILES": {
                "/Config/ServerState": 1,
                "/FavIcon.ico": 1
            },
            "SYMBOLACCESS": 0,
            "SYMBOLS": {
                "DefaultAuthExtension": 1,
                "DefaultUserGroup": 1,
                "GetCurrentUser": 3,
                "GetSymbolAccess": 3,
                "Heartbeat": 3,
                "IsAuthRequired": 3,
                "ListDomains": 3,
                "ListUserNames": 3,
                "Login": 3,
                "Logout": 3,
                "SetLocale": 3,
                "Unsubscribe": 3,
                "UserSelectType": 1
            }
        },
        "__SystemMaintenanceUsers": {
            "ENABLED": true,
            "SYMBOLACCESS": 0
        },
        "__SystemUsers": {
            "ENABLED": true,
            "FILEACCESS": 3,
            "FILES": {
                "/Config": 1
            },
            "SYMBOLACCESS": 0,
            "SYMBOLS": {
                "ChangeUserSettings": 3,
                "ConfirmAlarm": 3,
                "CreateEvent": 3,
                "DefaultAuthExtension": 1,
                "DefaultUserGroup": 1,
                "Diagnostics": 3,
                "Export": 3,
                "GetConfiguration": 3,
                "GetCurrentUser": 3,
                "GetDefinitions": 3,
                "GetFileInformation": 3,
                "GetSchema": 3,
                "GetServerInformation": 3,
                "GetSymbolAccess": 3,
                "Heartbeat": 3,
                "IsAuthRequired": 3,
                "ListDomains": 3,
                "ListEvents": 3,
                "ListSymbols": 3,
                "ListUserNames": 3,
                "LocalizeText": 3,
                "Login": 3,
                "Logout": 3,
                "SetLocale": 3,
                "SubscribeEvents": 3,
                "TcHmiUserManagement.GetComplexityRules": 3,
                "Unsubscribe": 3,
                "UnsubscribeEvents": 3,
                "UpdateEventsSubscription": 3,
                "UserSelectType": 1
            }
        }
    },
    "required": [
        "__SystemAdministrators",
        "__SystemUsers",
        "__SystemMaintenanceUsers",
        "__SystemGuests"
    ],
    "type": "object"
}
```
