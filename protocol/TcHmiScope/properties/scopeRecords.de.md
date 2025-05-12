# Scope-Aufnahmen.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiScope"` |
| Vollständiger Symbol-Pfad | `"TcHmiScope.Config::scopeRecords"` |
| Sichtbarkeit | HideInEngineering |
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
            "symbol": "TcHmiScope.Config::scopeRecords"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiScope.Config::scopeRecords', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiScope.Config::scopeRecords=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "items": {
        "properties": {
            "headlessServer": {
                "type": "string"
            },
            "headlessServerConnectionId": {
                "type": "string"
            },
            "scopeConfigName": {
                "type": "string"
            },
            "serverHandles": {
                "items": {
                    "properties": {
                        "guid": {
                            "type": "string"
                        },
                        "serverHandle": {
                            "type": "integer"
                        }
                    },
                    "required": [
                        "guid",
                        "serverHandle"
                    ],
                    "type": "object"
                },
                "type": "array"
            },
            "targetConnectionIds": {
                "items": {
                    "properties": {
                        "connectionId": {
                            "type": "integer"
                        },
                        "target": {
                            "type": "string"
                        },
                        "targetNetId": {
                            "type": "string"
                        }
                    },
                    "required": [
                        "connectionId",
                        "target",
                        "targetNetId"
                    ],
                    "type": "object"
                },
                "type": "array"
            },
            "triggerHandles": {
                "items": {
                    "properties": {
                        "clientTriggerHandle": {
                            "type": "integer"
                        },
                        "groupHandle": {
                            "type": "integer"
                        },
                        "guid": {
                            "type": "string"
                        }
                    },
                    "required": [
                        "guid",
                        "groupHandle",
                        "clientTriggerHandle"
                    ],
                    "type": "object"
                },
                "type": "array"
            }
        },
        "required": [
            "scopeConfigName",
            "headlessServerConnectionId",
            "serverHandles",
            "triggerHandles",
            "targetConnectionIds"
        ],
        "type": "object"
    },
    "readOnly": true,
    "type": "array",
    "visibility": "HideInEngineering"
}
```
