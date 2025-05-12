# Get the schema of a specific dynamic symbol.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiOpcUa"` |
| Vollständiger Symbol-Pfad | `"TcHmiOpcUa.GetSchema"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

Get the JSON schema of a specific OPC UA variable.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiOpcUa.GetSchema",
            "writeValue": "Root::basic::PLC::DataBlocksGlobal::GlobalDB_SimpleDataTypes_Typesafe::MyInt"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

Get the JSON schema of a specific OPC UA variable.
```javascript
TcHmi.Server.writeSymbol('TcHmiOpcUa.GetSchema',
    "Root::basic::PLC::DataBlocksGlobal::GlobalDB_SimpleDataTypes_Typesafe::MyInt",
    data => {
        if (data.error !== TcHmi.Errors.NONE ||
            data.response.error ||
            data.response.commands[0].error) {
            // Handle error(s)...
            return;
        }
        // Handle result...
        console.info(
            'TcHmiOpcUa.GetSchema=' +
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
    "writeValue": {
        "type": "string"
    }
}
```
