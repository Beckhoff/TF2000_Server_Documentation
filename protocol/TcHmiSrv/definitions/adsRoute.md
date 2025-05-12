# ADS route

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Implicit access is allowed | Yes |

## JSON schema

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
