# Import data into the configuration databases.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"Import"` |
| Category | configurationsAndFilesystem |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Import a configuration database.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Import",
            "writeValue": {
                "apiVersion": 9.0,
                "commands": [
                    {
                        "commandOptions": [
                            "SendWriteValue"
                        ],
                        "symbol": "EXTENSION_NAME.Config",
                        "symbolOptions": {
                            "configVersion": "1.0.0.0"
                        },
                        "writeValue": {
                            "VAR1": [],
                            "VAR2": 3
                        }
                    }
                ],
                "id": 0.0,
                "requestType": "ReadWrite"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

Import a configuration database.
```javascript
TcHmi.Server.writeSymbol('Import',
    {
        "apiVersion": 9.0,
        "commands": [
            {
                "commandOptions": [
                    "SendWriteValue"
                ],
                "symbol": "EXTENSION_NAME.Config",
                "symbolOptions": {
                    "configVersion": "1.0.0.0"
                },
                "writeValue": {
                    "VAR1": [],
                    "VAR2": 3
                }
            }
        ],
        "id": 0.0,
        "requestType": "ReadWrite"
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
            'Import=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "category": "configurationsAndFilesystem",
    "readValue": {
        "function": true
    },
    "writeValue": {
        "$ref": "tchmi:general#/definitions/Any"
    }
}
```
