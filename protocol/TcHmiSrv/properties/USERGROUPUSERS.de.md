# Die Account-Einstellungen und Gruppenmitgliedschaften aller Benutzer aller Authentifizierungserweiterungen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"TcHmiSrv.Config::USERGROUPUSERS"` |
| Sichtbarkeit | AlwaysShow |
| Standardmäßig in jeder Konfiguration enthalten | Nein |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSrv.Config::USERGROUPUSERS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::USERGROUPUSERS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::USERGROUPUSERS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
{
    "TcHmiUserManagement": {
        "__SystemAdministrator": {
            "USERGROUPUSERS_GROUPS": [
                "__SystemAdministrators"
            ],
            "USERGROUPUSERS_LOCALE": "project"
        },
        "__SystemGuest": {
            "USERGROUPUSERS_GROUPS": [
                "__SystemGuests"
            ],
            "USERGROUPUSERS_LOCALE": "project"
        },
        "__SystemUser": {
            "USERGROUPUSERS_GROUPS": [
                "__SystemUsers"
            ],
            "USERGROUPUSERS_LOCALE": "project"
        }
    }
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "additionalProperties": {
            "additionalProperties": false,
            "configDescription": "DESC_USERNAME",
            "keyOptionMethod": {
                "symbol": "ListUserNames"
            },
            "properties": {
                "USERGROUPUSERS_AUTO_LOGOFF": {
                    "default": "PT0S",
                    "format": "timespan",
                    "type": "string"
                },
                "USERGROUPUSERS_FORCE_2FA_INIT": {
                    "default": false,
                    "type": "boolean"
                },
                "USERGROUPUSERS_FORCE_PASSWORD_CHANGE": {
                    "default": false,
                    "type": "boolean"
                },
                "USERGROUPUSERS_GROUPS": {
                    "$ref": "tchmi:server#/definitions/userGroups"
                },
                "USERGROUPUSERS_LOCALE": {
                    "allOf": [
                        {
                            "$ref": "tchmi:server#/definitions/userLocale"
                        },
                        {
                            "configDescription": "DESC_LOCALE"
                        }
                    ]
                },
                "USERGROUPUSERS_TIMEFORMATLOCALE": {
                    "allOf": [
                        {
                            "$ref": "tchmi:server#/definitions/userLocale"
                        },
                        {
                            "configDescription": "DESC_LOCALE"
                        }
                    ]
                },
                "USERGROUPUSERS_TIMEZONE": {
                    "allOf": [
                        {
                            "$ref": "tchmi:server#/definitions/userTimeZone"
                        },
                        {
                            "configDescription": "DESC_TIMEZONE"
                        }
                    ]
                }
            },
            "required": [
                "USERGROUPUSERS_LOCALE",
                "USERGROUPUSERS_GROUPS",
                "USERGROUPUSERS_AUTO_LOGOFF"
            ],
            "type": "object"
        },
        "configDescription": "DESC_AUTHENTICATION_DOMAIN",
        "type": "object"
    },
    "default": {
        "TcHmiUserManagement": {
            "__SystemAdministrator": {
                "USERGROUPUSERS_GROUPS": [
                    "__SystemAdministrators"
                ],
                "USERGROUPUSERS_LOCALE": "project"
            },
            "__SystemGuest": {
                "USERGROUPUSERS_GROUPS": [
                    "__SystemGuests"
                ],
                "USERGROUPUSERS_LOCALE": "project"
            },
            "__SystemUser": {
                "USERGROUPUSERS_GROUPS": [
                    "__SystemUsers"
                ],
                "USERGROUPUSERS_LOCALE": "project"
            }
        }
    },
    "required": [
        "TcHmiUserManagement"
    ],
    "type": "object"
}
```
