# Zielsysteme können viele ADS-Ports haben. Die meisten werden nur selten in HMI-Projekten verwendet.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"ADS"` |
| Vollständiger Symbol-Pfad | `"ADS.Config::VISIBLE_RUNTIME_PORTS"` |
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
            "symbol": "ADS.Config::VISIBLE_RUNTIME_PORTS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

```javascript
TcHmi.Server.readSymbol('ADS.Config::VISIBLE_RUNTIME_PORTS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ADS.Config::VISIBLE_RUNTIME_PORTS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Typ | `"array"` |
| Impliziter Zugriff erlaubt | Ja |

## Default-Wert

```json
[
    301,
    302,
    303,
    304,
    350,
    351,
    352,
    353,
    354,
    355,
    501,
    801,
    811,
    821,
    831,
    851,
    852,
    853,
    854,
    10000,
    19800
]
```

## JSON-Schema

```json
{
    "default": [
        301,
        302,
        303,
        304,
        350,
        351,
        352,
        353,
        354,
        355,
        501,
        801,
        811,
        821,
        831,
        851,
        852,
        853,
        854,
        10000,
        19800
    ],
    "items": {
        "allOf": [
            {
                "$ref": "tchmi:general#/definitions/UINT16"
            },
            {
                "minimum": 1
            }
        ]
    },
    "propertyOrder": 6,
    "type": "array",
    "visibility": "HideInEngineering"
}
```
