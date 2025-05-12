# Qualified name

## General information

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "properties": {
        "Name": {
            "type": "string"
        },
        "NamespaceIndex": {
            "type": "integer"
        }
    },
    "required": [
        "NamespaceIndex",
        "Name"
    ],
    "type": "object"
}
```
