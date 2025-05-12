# Zu allen aktiven Laufzeiten wird eine ADS-Verbindung hergestellt.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.Config::RUNTIMES"` |
| Sichtbarkeit | AlwaysShow |
| Standardmäßig in jeder Konfiguration enthalten | Ja |

## Beispiel-Anfrage - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ADS.Config::RUNTIMES"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::RUNTIMES', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::RUNTIMES=' +
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
    "PLC1": {
        "ENABLED": true,
        "NETID": "127.0.0.1.1.1",
        "PORT": 851,
        "READ_ONLY": false,
        "SYMBOLS": {},
        "USE_WHITELISTING": false
    }
}
```

## JSON-Schema

```json
{
    "additionalProperties": {
        "additionalProperties": false,
        "configDescription": "DESC_RUNTIME",
        "properties": {
            "ENABLED": {
                "default": true,
                "propertyOrder": 1,
                "type": "boolean"
            },
            "NETID": {
                "allOf": [
                    {
                        "$ref": "tchmi:server#/definitions/adsRoute"
                    },
                    {
                        "configDescription": "DESC_ADS_ROUTE",
                        "propertyOrder": 2
                    }
                ]
            },
            "PORT": {
                "default": 851,
                "minimum": 0,
                "optionMethod": {
                    "symbol": "{domain}.RuntimePorts",
                    "writeValue": {
                        "NETID": {
                            "$data": "#/properties/RUNTIMES/additionalProperties/NETID"
                        }
                    }
                },
                "propertyOrder": 3,
                "type": "integer"
            },
            "READ_ONLY": {
                "configDescription": "DESC_READ_ONLY",
                "default": false,
                "propertyOrder": 5,
                "type": "boolean"
            },
            "SYMBOLS": {
                "additionalProperties": {
                    "configDescription": "DESC_SYMBOL",
                    "properties": {
                        "INDEXGROUP": {
                            "$ref": "tchmi:general#/definitions/UINT32"
                        },
                        "INDEXOFFSET": {
                            "$ref": "tchmi:general#/definitions/UINT32"
                        },
                        "TYPENAME": {
                            "configDescription": "DESC_TYPENAME",
                            "optionMethod": {
                                "symbol": "{domain}.ListCommonTypes"
                            },
                            "type": "string"
                        }
                    },
                    "required": [
                        "INDEXGROUP",
                        "INDEXOFFSET",
                        "TYPENAME"
                    ],
                    "type": "object"
                },
                "default": {},
                "propertyOrder": 6,
                "type": "object"
            },
            "USE_WHITELISTING": {
                "default": false,
                "propertyOrder": 4,
                "type": "boolean"
            }
        },
        "required": [
            "PORT",
            "USE_WHITELISTING",
            "NETID",
            "ENABLED",
            "SYMBOLS",
            "READ_ONLY"
        ],
        "type": "object"
    },
    "configDescription": "DESC_RUNTIMES",
    "default": {
        "PLC1": {
            "ENABLED": true,
            "NETID": "127.0.0.1.1.1",
            "PORT": 851,
            "READ_ONLY": false,
            "SYMBOLS": {},
            "USE_WHITELISTING": false
        }
    },
    "defaultConfigurable": true,
    "propertyOrder": 1,
    "type": "object"
}
```
