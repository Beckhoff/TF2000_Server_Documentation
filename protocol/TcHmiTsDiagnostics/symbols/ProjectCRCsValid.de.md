# Get information about the project CRC of a specific safety project.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiTsDiagnostics"` |
| Vollständiger Symbol-Pfad | `"TcHmiTsDiagnostics.ProjectCRCsValid"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| device | string |
| safetyProject | string |

## Beispiel-Anfrage - WebSocket

Get information about the project CRC of the safety project from 'Device1' and 'Controller1'.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiTsDiagnostics.ProjectCRCsValid",
            "writeValue": {
                "device": "Device1",
                "safetyProject": "Controller1"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get information about the project CRC of the safety project from 'Device1' and 'Controller1'.
```javascript
TcHmi.Server.writeSymbol('TcHmiTsDiagnostics.ProjectCRCsValid',
    {
        "device": "Device1",
        "safetyProject": "Controller1"
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
            'TcHmiTsDiagnostics.ProjectCRCsValid=' +
            data.response.commands[0].readValue);
    }
);
```

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "readValue": {
        "properties": {
            "projectCrcValid": {
                "type": "boolean"
            }
        },
        "type": "object"
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "device": {
                "type": "string"
            },
            "safetyProject": {
                "type": "string"
            }
        },
        "required": [
            "device",
            "safetyProject"
        ],
        "type": "object"
    }
}
```
