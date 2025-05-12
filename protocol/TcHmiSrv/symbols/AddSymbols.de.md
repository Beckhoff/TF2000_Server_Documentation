# Map some dynamic symbols automatically.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"AddSymbols"` |
| Kategorie | symbols |
| Sichtbarkeit | AlwaysShow |

## Parameter

|  |  |
| - | - |
| domain | string |
| path | string |
| namePrefix | string |
| dryRun | boolean |
| ignoreProblems | boolean |
| ignore | array |
| skipExisting | boolean |
| options | object |
| limit |  |

## Beispiel-Anfrage - WebSocket

Map some of the dynamic symbols of the ADS domain automatically.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "AddSymbols",
            "writeValue": {
                "domain": "ADS"
            }
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Map some of the dynamic symbols of the ADS domain automatically.
```javascript
TcHmi.Server.writeSymbol('AddSymbols',
    {
        "domain": "ADS"
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
            'AddSymbols=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON-Schema

```json
{
    "category": "symbols",
    "readValue": {
        "additionalProperties": {
            "oneOf": [
                {
                    "type": "boolean"
                },
                {
                    "$ref": "tchmi:general#/definitions/errorDetails"
                }
            ]
        },
        "function": true,
        "type": "object"
    },
    "writeValue": {
        "properties": {
            "domain": {
                "type": "string"
            },
            "dryRun": {
                "default": false,
                "type": "boolean"
            },
            "ignore": {
                "default": [],
                "items": {
                    "type": "string"
                },
                "type": "array",
                "uniqueItems": true
            },
            "ignoreProblems": {
                "default": false,
                "type": "boolean"
            },
            "limit": {
                "allOf": [
                    {
                        "$ref": "tchmi:general#/definitions/INT32"
                    },
                    {
                        "default": 1000,
                        "minimum": 1
                    }
                ]
            },
            "namePrefix": {
                "default": "",
                "type": "string"
            },
            "options": {
                "additionalProperties": {},
                "type": "object"
            },
            "path": {
                "default": "",
                "type": "string"
            },
            "skipExisting": {
                "default": false,
                "type": "boolean"
            }
        },
        "required": [
            "domain"
        ],
        "type": "object"
    }
}
```
