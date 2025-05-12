# ADS-Route

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Typ | `"string"` |
| Impliziter Zugriff erlaubt | Ja |

## JSON-Schema

```json
{
    "allOf": [
        {
            "oneOf": [
                {
                    "format": "ipv4"
                },
                {
                    "format": "amsnetid"
                }
            ]
        },
        {
            "description": "descAdsRoute",
            "optionMethod": {
                "symbol": "ADS.ListRoutes"
            },
            "type": "string"
        }
    ]
}
```
