# Depending on the size of the directory, the search might take too long or return too many results. If disabled, the usernames are collected from the TcHmiSrv configuration.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiLdap"` |
| Full symbol path | `"TcHmiLdap.Config::USE_LDAP_SEARCH_FOR_LISTUSERS"` |
| Category | authentication |
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
            "symbol": "TcHmiLdap.Config::USE_LDAP_SEARCH_FOR_LISTUSERS"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiLdap.Config::USE_LDAP_SEARCH_FOR_LISTUSERS', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiLdap.Config::USE_LDAP_SEARCH_FOR_LISTUSERS=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"boolean"` |
| Implicit access is allowed | Yes |
| Default value | `False` |

## JSON schema

```json
{
    "category": "authentication",
    "configDescription": "DESC_USE_LDAP_SEARCH_FOR_LISTUSERS",
    "default": false,
    "propertyOrder": 15,
    "type": "boolean"
}
```
