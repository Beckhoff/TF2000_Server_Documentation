# Server extensions are used to integrate additional functionality into the server.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::EXTENSIONS"` |
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
            "symbol": "TcHmiSrv.Config::EXTENSIONS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::EXTENSIONS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::EXTENSIONS=' +
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
    "ADS": {
        "NAME": "TcHmiAds",
        "PATH": "TcHmiAds",
        "REQUIRED": true,
        "STARTUPTYPE": 1
    },
    "TcHmiLua": {
        "NAME": "TcHmiLua",
        "PATH": "TcHmiLua",
        "REQUIRED": true,
        "STARTUPTYPE": 0
    },
    "TcHmiSqliteLogger": {
        "NAME": "TcHmiSqliteLogger",
        "PATH": "TcHmiSqliteLogger",
        "REQUIRED": true,
        "STARTUPTYPE": 0
    },
    "TcHmiUserManagement": {
        "NAME": "TcHmiUserManagement",
        "PATH": "TcHmiUserManagement",
        "REQUIRED": true,
        "STARTUPTYPE": 1
    }
}
```

## JSON schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "properties": {
            "ENABLED": {
                "default": true,
                "type": "boolean"
            },
            "METADATA": {
                "allOf": [
                    {
                        "$ref": "tchmi:general#/definitions/Any"
                    },
                    {
                        "default": {
                            "migrationVersion": "1.14"
                        },
                        "visibility": "AlwaysHide"
                    }
                ]
            },
            "NAME": {
                "type": "string"
            },
            "PATH": {
                "configDescription": "DESC_EXTENSION_PATH",
                "format": "filename",
                "type": "string"
            },
            "PROCESSID": {
                "default": -1,
                "type": "integer",
                "visibility": "HideInEngineering"
            },
            "REQUIRED": {
                "default": false,
                "readOnly": true,
                "type": "boolean"
            },
            "STARTUPTYPE": {
                "$ref": "tchmi:server#/definitions/timing"
            }
        },
        "readOnly": {
            "$data": "#/properties/EXTENSIONS/additionalProperties/properties/REQUIRED"
        },
        "required": [
            "NAME",
            "ENABLED",
            "STARTUPTYPE"
        ],
        "title": "TITLE_EXTENSION",
        "type": "object"
    },
    "default": {
        "ADS": {
            "NAME": "TcHmiAds",
            "PATH": "TcHmiAds",
            "REQUIRED": true,
            "STARTUPTYPE": 1
        },
        "TcHmiLua": {
            "NAME": "TcHmiLua",
            "PATH": "TcHmiLua",
            "REQUIRED": true,
            "STARTUPTYPE": 0
        },
        "TcHmiSqliteLogger": {
            "NAME": "TcHmiSqliteLogger",
            "PATH": "TcHmiSqliteLogger",
            "REQUIRED": true,
            "STARTUPTYPE": 0
        },
        "TcHmiUserManagement": {
            "NAME": "TcHmiUserManagement",
            "PATH": "TcHmiUserManagement",
            "REQUIRED": true,
            "STARTUPTYPE": 1
        }
    },
    "required": [
        "TcHmiSqliteLogger",
        "TcHmiLua",
        "TcHmiUserManagement",
        "ADS"
    ],
    "type": "object"
}
```
