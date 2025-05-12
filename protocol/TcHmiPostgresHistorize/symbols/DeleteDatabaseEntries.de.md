# Löscht Einträge in der Historize-Datenbank.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiPostgresHistorize.DeleteDatabaseEntries"` |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| symbolName | string |
| disableRecording | boolean |

## Beispiel-Anfrage - WebSocket

Disable recording and delete database entries of 'MySymbol'. If 'symbolName' is not set all entries in the database will be deleted. 'disableRecording' disables the recording of one or all historize symbols depending if 'symbolName' is set.'
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiPostgresHistorize.DeleteDatabaseEntries",
            "writeValue": {
                "disableRecording": true,
                "symbolName": "MySymbol"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Disable recording and delete database entries of 'MySymbol'. If 'symbolName' is not set all entries in the database will be deleted. 'disableRecording' disables the recording of one or all historize symbols depending if 'symbolName' is set.'
```javascript
TcHmi.Server.writeSymbol('TcHmiPostgresHistorize.DeleteDatabaseEntries',
    {
        "disableRecording": true,
        "symbolName": "MySymbol"
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
            'TcHmiPostgresHistorize.DeleteDatabaseEntries=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true
    },
    "userGroups": [
        "__SystemUsers"
    ],
    "writeValue": {
        "properties": {
            "disableRecording": {
                "type": "boolean"
            },
            "symbolName": {
                "type": "string"
            }
        },
        "type": "object"
    }
}
```
