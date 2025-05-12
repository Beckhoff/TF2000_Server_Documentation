# When the 'ListEvents' function symbol is called, the events are requested from the default event extension.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::DEFAULTEVENTEXTENSION"` |
| Category | advanced |
| Visibility | HideInEngineering |
| Contained in every configuration by default | No |

## Sample request - WebSocket

```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "TcHmiSrv.Config::DEFAULTEVENTEXTENSION"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::DEFAULTEVENTEXTENSION', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::DEFAULTEVENTEXTENSION=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"string"` |
| Implicit access is allowed | Yes |
| Default value | `"TcHmiSqliteLogger"` |

## JSON schema

```json
{
    "category": "advanced",
    "default": "TcHmiSqliteLogger",
    "type": "string",
    "visibility": "HideInEngineering"
}
```
