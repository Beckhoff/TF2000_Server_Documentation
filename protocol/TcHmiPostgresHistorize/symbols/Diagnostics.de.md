# Ruft Informationen über die in der Datenbank gespeicherten historisierten Daten ab.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiPostgresHistorize"` |
| Vollständiger Symbol-Pfad | `"TcHmiPostgresHistorize.Diagnostics"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiPostgresHistorize.Diagnostics"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiPostgresHistorize.Diagnostics', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiPostgresHistorize.Diagnostics=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "function": true,
        "properties": {
            "connectionState": {
                "enum": [
                    "Connected",
                    "Not Connected",
                    "Pending"
                ],
                "propertyOrder": 1,
                "readOnly": true,
                "type": "string"
            },
            "databaseSize": {
                "allOf": [
                    {
                        "$ref": "tchmi:general#/definitions/INT64"
                    },
                    {
                        "description": "descDatabaseSize",
                        "displayClass": "byte",
                        "propertyOrder": 4,
                        "readOnly": true
                    }
                ]
            },
            "domainError": {
                "format": "multiline",
                "propertyOrder": 3,
                "type": "string"
            },
            "domainState": {
                "enum": [
                    "Good",
                    "Bad"
                ],
                "propertyOrder": 2,
                "type": "string"
            },
            "numEntries": {
                "propertyOrder": 5,
                "readOnly": true,
                "type": "integer"
            }
        },
        "required": [
            "domainState",
            "connectionState"
        ],
        "type": "object"
    }
}
```
