# This list contains all configured alarm symbols.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiAlarm"` |
| Full symbol path | `"TcHmiAlarm.Config::alarmSymbols"` |
| Visibility | AlwaysShow |
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
            "symbol": "TcHmiAlarm.Config::alarmSymbols"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiAlarm.Config::alarmSymbols', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiAlarm.Config::alarmSymbols=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"object"` |
| Implicit access is allowed | Yes |

## JSON schema

```json
{
    "additionalProperties": {
        "configDescription": "DESC_ALARM_SYMBOL",
        "keyOptionMethod": {
            "symbol": "ListSymbolNames"
        },
        "properties": {
            "alarmSettings": {
                "additionalProperties": {
                    "additionalProperties": false,
                    "configDescription": "alarmSetting",
                    "properties": {
                        "alarmTextKey": {
                            "propertyOrder": 9,
                            "type": "string"
                        },
                        "condition": {
                            "allOf": [
                                {
                                    "$ref": "tchmi:server#/definitions/filter"
                                },
                                {
                                    "minItems": 1
                                },
                                {
                                    "configDescription": "DESC_CONDITION",
                                    "propertyOrder": 8
                                }
                            ]
                        },
                        "enabled": {
                            "default": true,
                            "propertyOrder": 1,
                            "type": "boolean"
                        },
                        "notificationType": {
                            "default": 1,
                            "enum": [
                                0,
                                1,
                                2
                            ],
                            "options": [
                                {
                                    "label": "enum_0_message",
                                    "value": 0
                                },
                                {
                                    "label": "enum_1_alarm_with_confirmation",
                                    "value": 1
                                },
                                {
                                    "label": "enum_2_alarm",
                                    "value": 2
                                }
                            ],
                            "propertyOrder": 2,
                            "type": "integer"
                        },
                        "severity": {
                            "$ref": "tchmi:server#/definitions/severity",
                            "propertyOrder": 3
                        }
                    },
                    "required": [
                        "severity",
                        "condition",
                        "notificationType",
                        "enabled"
                    ],
                    "title": "alarmSetting",
                    "type": "object"
                },
                "propertyOrder": 3,
                "type": "object"
            },
            "enabled": {
                "default": true,
                "propertyOrder": 0,
                "type": "boolean"
            },
            "interval": {
                "default": "PT1S",
                "format": "timespan",
                "formatMinimum": "PT0.01S",
                "propertyOrder": 2,
                "type": "string"
            },
            "onError": {
                "configDescription": "DESC_ON_ERROR",
                "default": false,
                "propertyOrder": 1,
                "type": "boolean",
                "visibility": "HideInEngineering"
            },
            "version": {
                "default": 1.0,
                "optionMethod": {
                    "orderBy": "DESC",
                    "symbol": "GetSchema::{key}",
                    "writeValue": {
                        "resolve": "AllVersions",
                        "symbol": {
                            "$data": "#/properties/alarmSymbols/additionalProperties"
                        }
                    }
                },
                "optionMethodAllowCustom": false,
                "type": "number"
            }
        },
        "required": [
            "alarmSettings",
            "enabled",
            "onError",
            "interval"
        ],
        "title": "titleAlarmSymbol",
        "type": "object"
    },
    "configDescription": "DESC_ALARM_SYMBOLS",
    "propertyOrder": 2,
    "type": "object"
}
```
