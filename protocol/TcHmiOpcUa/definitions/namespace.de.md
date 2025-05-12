# OPC-UA-Namensraum

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |

## Schema

|  |  |
| - | - |
| Typ | `"object"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "additionalProperties": false,
    "properties": {
        "advanced": {
            "optionMethod": {
                "symbol": "{domain}.Config::advancedSettings"
            },
            "propertyOrder": 3,
            "type": "string"
        },
        "connection": {
            "optionMethod": {
                "symbol": "{domain}.Config::connectionSettings"
            },
            "propertyOrder": 4,
            "type": "string"
        },
        "endpoint": {
            "default": "opc.tcp://127.0.0.1:4840",
            "propertyOrder": 1,
            "type": "string"
        },
        "security": {
            "optionMethod": {
                "symbol": "{domain}.Config::securitySettings"
            },
            "propertyOrder": 2,
            "type": "string"
        }
    },
    "required": [
        "endpoint",
        "advanced",
        "connection",
        "security"
    ],
    "type": "object"
}
```
