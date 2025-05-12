# The SessionId of the logged in user.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"Login"` |
| Category | usersAndSessions |
| Visibility | AlwaysShow |

## Parameters

|  |  |
| - | - |
| userName | string |
| password | string |
| persistent | boolean |
| maintenanceMode | boolean |
| persistPreviousSession | boolean |

## Sample request - WebSocket

Login user `HmiUser` with password `test`.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Login",
            "writeValue": {
                "password": "test",
                "userName": "HmiUser"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Login user `HmiUser` with password `test`.
```javascript
TcHmi.Server.writeSymbol('Login',
    {
        "password": "test",
        "userName": "HmiUser"
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
            'Login=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "usersAndSessions",
    "readValue": {
        "description": "The SessionId of the logged in user.",
        "function": true,
        "type": "string"
    },
    "writeValue": {
        "properties": {
            "maintenanceMode": {
                "default": false,
                "type": "boolean"
            },
            "password": {
                "format": "masked",
                "type": "string"
            },
            "persistPreviousSession": {
                "default": false,
                "type": "boolean"
            },
            "persistent": {
                "default": false,
                "type": "boolean"
            },
            "userName": {
                "type": "string"
            }
        },
        "required": [
            "userName",
            "password"
        ],
        "type": "object"
    }
}
```
