# Get information about the current state of the HMI server.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"Diagnostics"` |
| Visibility | AlwaysShow |

## Sample request - WebSocket

Server-Time Subscription
```json
{
    "commands": [
        {
            "commandOptions": [
                "SendErrorMessage",
                "SendWriteValue"
            ],
            "symbol": "Diagnostics::SERVERTIME"
        }
    ],
    "requestType": "Subscription"
}
```

## Sample request - JavaScript

Server-Time Subscription
```javascript
TcHmi.Server.request('Diagnostics::SERVERTIME',
    {
        "commands": [
            {
                "commandOptions": [
                    "SendErrorMessage",
                    "SendWriteValue"
                ],
                "symbol": "Diagnostics::SERVERTIME"
            }
        ],
        "requestType": "Subscription"
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
            'Diagnostics=' +
            data.response.commands[0].readValue);
    }
);
```

## JSON schema

```json
{
    "readValue": {
        "additionalProperties": false,
        "function": true,
        "properties": {
            "ACCEPTEDSOCKETS": {
                "type": "integer"
            },
            "ACTIVESESSIONS": {
                "link": "Sessions",
                "type": "integer"
            },
            "ACTIVESOCKETS": {
                "type": "integer"
            },
            "ARCHITECTURE": {
                "type": "string"
            },
            "DISCOVERY_RUNNING": {
                "type": "boolean",
                "visibility": "HideInEngineering"
            },
            "DOTNETCLASSICVERSIONS": {
                "items": {
                    "type": "string"
                },
                "type": "array"
            },
            "DOTNETCOREVERSIONS": {
                "items": {
                    "type": "string"
                },
                "type": "array"
            },
            "DOTNETVERSIONS": {
                "items": {
                    "type": "string"
                },
                "type": "array"
            },
            "LICENSE": {
                "properties": {
                    "CLIENTS": {
                        "propertyOrder": 2,
                        "type": "integer"
                    },
                    "EXTENSIONS": {
                        "propertyOrder": 6,
                        "type": "boolean"
                    },
                    "SERVERS": {
                        "propertyOrder": 1,
                        "type": "integer"
                    },
                    "STATE": {
                        "default": "Unregistered",
                        "enum": [
                            "Error",
                            "Unregistered",
                            "Engineering",
                            "Demo",
                            "Pending",
                            "OK"
                        ],
                        "propertyOrder": 7,
                        "type": "string"
                    },
                    "TARGETS": {
                        "propertyOrder": 4,
                        "type": "integer"
                    },
                    "USEDCLIENTS": {
                        "propertyOrder": 3,
                        "type": "integer"
                    },
                    "USEDTARGETS": {
                        "propertyOrder": 5,
                        "type": "integer"
                    }
                },
                "type": "object"
            },
            "MEMORYUSAGE": {
                "type": "number",
                "unit": "megabyte"
            },
            "REMOTESERVERS": {
                "additionalProperties": {
                    "properties": {
                        "REMOTE_ERROR": {
                            "$ref": "tchmi:general#/definitions/errorDetails"
                        },
                        "REMOTE_STATUS": {
                            "enum": [
                                "Disconnected",
                                "Connected",
                                "Error",
                                "Disabled"
                            ],
                            "propertyOrder": 1,
                            "type": "string"
                        }
                    },
                    "required": [
                        "REMOTE_STATUS"
                    ],
                    "type": "object"
                },
                "type": "object"
            },
            "SERVERTIME": {
                "format": "date-time",
                "type": "string"
            },
            "TRAFFICIN": {
                "type": "number",
                "unit": "byte"
            },
            "TRAFFICOUT": {
                "type": "number",
                "unit": "byte"
            },
            "UPTIME": {
                "format": "timespan",
                "type": "string"
            }
        },
        "type": "object"
    }
}
```
