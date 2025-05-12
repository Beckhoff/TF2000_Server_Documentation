# Enthält Informationen über alle verwalteten Benutzerkonten.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiUserManagement"` |
| Vollständiger Symbol-Pfad | `"TcHmiUserManagement.Config::USERS"` |
| Sichtbarkeit | AlwaysHide |
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
            "symbol": "TcHmiUserManagement.Config::USERS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiUserManagement.Config::USERS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiUserManagement.Config::USERS=' +
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
    "__SystemAdministrator": {
        "ENABLED": false,
        "PASSWORD": "",
        "SALT": ""
    },
    "__SystemGuest": {
        "ENABLED": true,
        "PASSWORD": "",
        "SALT": ""
    },
    "__SystemUser": {
        "ENABLED": true,
        "PASSWORD": "",
        "SALT": ""
    }
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "configDescription": "DESC_USER",
        "properties": {
            "ALGORITHM": {
                "default": 0,
                "enum": [
                    0,
                    1
                ],
                "options": [
                    {
                        "label": "SHA256",
                        "value": 0
                    },
                    {
                        "label": "PBKDF2-HMAC-64-SHA512-1000",
                        "value": 1
                    }
                ],
                "type": "integer"
            },
            "ENABLED": {
                "default": true,
                "type": "boolean"
            },
            "LAST_PASSWORD_CHANGE": {
                "format": "date-time",
                "type": "string"
            },
            "PASSWORD": {
                "default": "",
                "type": "string"
            },
            "SALT": {
                "default": "",
                "format": "base64",
                "type": "string"
            },
            "SECRET": {
                "properties": {
                    "algorithm": {
                        "default": 0,
                        "enum": [
                            0
                        ],
                        "options": [
                            {
                                "label": "SHA1",
                                "value": 0
                            }
                        ],
                        "type": "integer"
                    },
                    "configuration": {
                        "default": 0,
                        "enum": [
                            0
                        ],
                        "options": [
                            {
                                "label": "google-authenticator",
                                "value": 0
                            }
                        ],
                        "type": "integer"
                    },
                    "iv": {
                        "type": "string"
                    },
                    "value": {
                        "type": "string"
                    }
                },
                "type": "object"
            },
            "TWO_FACTOR_AUTHENTICATION_ENABLED": {
                "default": false,
                "type": "boolean"
            }
        },
        "required": [
            "PASSWORD",
            "SALT",
            "ALGORITHM",
            "ENABLED",
            "TWO_FACTOR_AUTHENTICATION_ENABLED"
        ],
        "type": "object"
    },
    "default": {
        "__SystemAdministrator": {
            "ENABLED": false,
            "PASSWORD": "",
            "SALT": ""
        },
        "__SystemGuest": {
            "ENABLED": true,
            "PASSWORD": "",
            "SALT": ""
        },
        "__SystemUser": {
            "ENABLED": true,
            "PASSWORD": "",
            "SALT": ""
        }
    },
    "required": [
        "__SystemAdministrator"
    ],
    "type": "object",
    "visibility": "AlwaysHide"
}
```
