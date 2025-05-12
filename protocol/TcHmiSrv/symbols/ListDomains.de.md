# Get list of registered domains.

## Allgemeine Informationen

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Vollständiger Symbol-Pfad | `"ListDomains"` |
| Sichtbarkeit | AlwaysShow |

## Beispiel-Anfrage - WebSocket

List all registered domains.
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "ListDomains"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Beispiel-Anfrage - JavaScript

List all registered domains.
```javascript
TcHmi.Server.readSymbol('ListDomains', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'ListDomains=' +
        data.response.commands[0].readValue);
});
```

## JSON-Schema

```json
{
    "readValue": {
        "additionalProperties": {
            "properties": {
                "authExtension": {
                    "description": "Shows if extension can be used for user management.",
                    "type": "boolean"
                },
                "configVersion": {
                    "description": "The version of the extension's configuration.",
                    "type": "string"
                },
                "debuggerAttached": {
                    "description": "Indicates whether a debugger is or will be attached to the extension.",
                    "type": "boolean"
                },
                "error": {
                    "$ref": "tchmi:general#/definitions/errorDetails"
                },
                "extension": {
                    "description": "The name of the extension.",
                    "type": "string"
                },
                "friendlyName": {
                    "description": "A more readable name version of the extension name.",
                    "type": "string"
                },
                "guid": {
                    "description": "The globally unique identifier associated with the extension.",
                    "type": "string"
                },
                "licensed": {
                    "description": "Indicate the extension is license status.",
                    "type": "boolean"
                },
                "packageVersion": {
                    "description": "The version of the NuGet package that contains the extension.",
                    "type": "string"
                },
                "remote": {
                    "description": "Shows if the domain refers to a remote server.",
                    "type": "boolean"
                },
                "required": {
                    "description": "Shows if the extension is considered to be required.",
                    "type": "boolean"
                },
                "state": {
                    "description": "Shows the current state of the extension.",
                    "enum": [
                        "NotLoaded",
                        "Loaded",
                        "Initialized",
                        "Invalid",
                        "Disabled",
                        "Unloading",
                        "NotRunning"
                    ],
                    "type": "string"
                },
                "thirdParty": {
                    "description": "Indicate the extension is a customer extension.",
                    "type": "boolean"
                },
                "updated": {
                    "description": "Shows last update time of the config.",
                    "format": "date-time",
                    "type": "string"
                },
                "version": {
                    "description": "The version of the extension.",
                    "type": "string"
                },
                "visibility": {
                    "description": "Indicates under which circumstances the extension configuration should be visible.",
                    "enum": [
                        "AlwaysShow",
                        "AlwaysHide",
                        "HideInEngineering"
                    ],
                    "type": "string"
                }
            },
            "type": "object"
        },
        "function": true,
        "type": "object"
    }
}
```
