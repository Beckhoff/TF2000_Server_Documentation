# Special handling and permissions for specific files or directories that match the given regular expression.

## General information

|  |  |
| - | - |
| Domain | `"TcHmiSrv"` |
| Full symbol path | `"TcHmiSrv.Config::FILESREGEX"` |
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
            "symbol": "TcHmiSrv.Config::FILESREGEX"
        }
    ],
    "requestType": "ReadWrite"
}
```

## Sample request - JavaScript

```javascript
TcHmi.Server.readSymbol('TcHmiSrv.Config::FILESREGEX', data => {
    if (data.error !== TcHmi.Errors.NONE ||
        data.response.error ||
        data.response.commands[0].error) {
        // Handle error(s)...
        return;
    }
    // Handle result...
    console.info(
        'TcHmiSrv.Config::FILESREGEX=' +
        data.response.commands[0].readValue);
});
```

## Schema

|  |  |
| - | - |
| Type | `"array"` |
| Implicit access is allowed | Yes |

## Default value

```json
[
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Security-Policy: frame-ancestors 'self' 127.0.0.1:* localhost:*\r\n Content-Type: text/html",
        "REGEX": ".*\\.(xml|htm|html|shtml)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: text/plain",
        "REGEX": ".*\\.(txt|view|content|usercontrol)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: text/xml",
        "REGEX": ".*\\.(config|xml)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: text/javascript",
        "REGEX": ".*\\.(js|mjs|jsonp)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: image/svg+xml",
        "REGEX": ".*\\.(svg)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: application/json",
        "REGEX": ".*\\.(json|map|localization|theme)$"
    },
    {
        "FILESHTTPHEADERS": "Content-Type: application/pdf",
        "REGEX": ".*\\.(pdf)$"
    },
    {
        "FILESHTTPHEADERS": "Content-Type: image/gif",
        "REGEX": ".*\\.(gif)$"
    },
    {
        "FILESHTTPHEADERS": "Content-Type: image/jpeg",
        "REGEX": ".*\\.(jpeg|jpg)$"
    },
    {
        "FILESHTTPHEADERS": "Content-Type: image/png",
        "REGEX": ".*\\.(png)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: image/bmp",
        "REGEX": ".*\\.(bmp)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: image/x-icon",
        "REGEX": ".*\\.(ico)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: text/css",
        "REGEX": ".*\\.(css)$"
    },
    {
        "FILESHTTPHEADERS": "Content-Type: application/octet-stream",
        "REGEX": ".*\\.(bin|dll|exe|img|iso)$"
    },
    {
        "FILESHTTPHEADERS": "Content-Type: application/java-archive",
        "REGEX": ".*\\.(ear|jar|war)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: vnd.ms-fontobject",
        "REGEX": ".*\\.(eot)$"
    },
    {
        "ENABLE_GZIP": true,
        "FILESHTTPHEADERS": "Content-Type: application/font-sfnt",
        "REGEX": ".*\\.(ttf|otf)$"
    },
    {
        "FILESHTTPHEADERS": "Content-Type: application/font-woff",
        "REGEX": ".*\\.(woff)$"
    },
    {
        "FILESHTTPHEADERS": "Content-Type: application/font-woff2",
        "REGEX": ".*\\.(woff2)$"
    },
    {
        "FILESHTTPHEADERS": "Content-Type: application/zip",
        "REGEX": ".*\\.(zip)$"
    },
    {
        "ENABLE_CACHE": false,
        "ENABLE_CHUNKING": false,
        "FILESHTTPHEADERS": "Content-Type: video/mp4",
        "REGEX": ".*\\.(mp4)$"
    },
    {
        "ENABLE_CACHE": false,
        "ENABLE_CHUNKING": false,
        "FILESHTTPHEADERS": "Content-Type: audio/mpeg",
        "REGEX": ".*\\.(mp3)$"
    },
    {
        "ENABLE_CACHE": false,
        "ENABLE_CHUNKING": false,
        "FILESHTTPHEADERS": "Content-Type: video/webm",
        "REGEX": ".*\\.(webm)$"
    },
    {
        "ENABLE_CACHE": false,
        "ENABLE_CHUNKING": false,
        "FILESHTTPHEADERS": "Content-Type: video/ogg",
        "REGEX": ".*\\.(ogg)$"
    },
    {
        "ENABLE_CACHE": false,
        "ENABLE_CHUNKING": false,
        "FILESHTTPHEADERS": "Content-Type: video/ogg",
        "REGEX": ".*\\.(ogv)$"
    },
    {
        "ENABLE_CACHE": false,
        "ENABLE_CHUNKING": false,
        "FILESHTTPHEADERS": "Content-Type: application/x-pem-file",
        "REGEX": ".*\\.(pem)$"
    },
    {
        "ENABLE_CACHE": false,
        "ENABLE_CHUNKING": false,
        "FILESHTTPHEADERS": "Content-Type: application/x-x509-ca-cert",
        "REGEX": ".*\\.(pem)$"
    }
]
```

## JSON schema

```json
{
    "default": [
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Security-Policy: frame-ancestors 'self' 127.0.0.1:* localhost:*\r\n Content-Type: text/html",
            "REGEX": ".*\\.(xml|htm|html|shtml)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: text/plain",
            "REGEX": ".*\\.(txt|view|content|usercontrol)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: text/xml",
            "REGEX": ".*\\.(config|xml)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: text/javascript",
            "REGEX": ".*\\.(js|mjs|jsonp)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: image/svg+xml",
            "REGEX": ".*\\.(svg)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: application/json",
            "REGEX": ".*\\.(json|map|localization|theme)$"
        },
        {
            "FILESHTTPHEADERS": "Content-Type: application/pdf",
            "REGEX": ".*\\.(pdf)$"
        },
        {
            "FILESHTTPHEADERS": "Content-Type: image/gif",
            "REGEX": ".*\\.(gif)$"
        },
        {
            "FILESHTTPHEADERS": "Content-Type: image/jpeg",
            "REGEX": ".*\\.(jpeg|jpg)$"
        },
        {
            "FILESHTTPHEADERS": "Content-Type: image/png",
            "REGEX": ".*\\.(png)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: image/bmp",
            "REGEX": ".*\\.(bmp)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: image/x-icon",
            "REGEX": ".*\\.(ico)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: text/css",
            "REGEX": ".*\\.(css)$"
        },
        {
            "FILESHTTPHEADERS": "Content-Type: application/octet-stream",
            "REGEX": ".*\\.(bin|dll|exe|img|iso)$"
        },
        {
            "FILESHTTPHEADERS": "Content-Type: application/java-archive",
            "REGEX": ".*\\.(ear|jar|war)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: vnd.ms-fontobject",
            "REGEX": ".*\\.(eot)$"
        },
        {
            "ENABLE_GZIP": true,
            "FILESHTTPHEADERS": "Content-Type: application/font-sfnt",
            "REGEX": ".*\\.(ttf|otf)$"
        },
        {
            "FILESHTTPHEADERS": "Content-Type: application/font-woff",
            "REGEX": ".*\\.(woff)$"
        },
        {
            "FILESHTTPHEADERS": "Content-Type: application/font-woff2",
            "REGEX": ".*\\.(woff2)$"
        },
        {
            "FILESHTTPHEADERS": "Content-Type: application/zip",
            "REGEX": ".*\\.(zip)$"
        },
        {
            "ENABLE_CACHE": false,
            "ENABLE_CHUNKING": false,
            "FILESHTTPHEADERS": "Content-Type: video/mp4",
            "REGEX": ".*\\.(mp4)$"
        },
        {
            "ENABLE_CACHE": false,
            "ENABLE_CHUNKING": false,
            "FILESHTTPHEADERS": "Content-Type: audio/mpeg",
            "REGEX": ".*\\.(mp3)$"
        },
        {
            "ENABLE_CACHE": false,
            "ENABLE_CHUNKING": false,
            "FILESHTTPHEADERS": "Content-Type: video/webm",
            "REGEX": ".*\\.(webm)$"
        },
        {
            "ENABLE_CACHE": false,
            "ENABLE_CHUNKING": false,
            "FILESHTTPHEADERS": "Content-Type: video/ogg",
            "REGEX": ".*\\.(ogg)$"
        },
        {
            "ENABLE_CACHE": false,
            "ENABLE_CHUNKING": false,
            "FILESHTTPHEADERS": "Content-Type: video/ogg",
            "REGEX": ".*\\.(ogv)$"
        },
        {
            "ENABLE_CACHE": false,
            "ENABLE_CHUNKING": false,
            "FILESHTTPHEADERS": "Content-Type: application/x-pem-file",
            "REGEX": ".*\\.(pem)$"
        },
        {
            "ENABLE_CACHE": false,
            "ENABLE_CHUNKING": false,
            "FILESHTTPHEADERS": "Content-Type: application/x-x509-ca-cert",
            "REGEX": ".*\\.(pem)$"
        }
    ],
    "items": {
        "allOf": [
            {
                "$ref": "tchmi:server#/definitions/fileSettings"
            },
            {
                "additionalProperties": true,
                "properties": {
                    "ENABLE_CACHE": {
                        "default": true,
                        "type": "boolean"
                    },
                    "ENABLE_CHUNKING": {
                        "default": true,
                        "type": "boolean"
                    },
                    "ENABLE_GZIP": {
                        "default": false,
                        "type": "boolean"
                    },
                    "REGEX": {
                        "type": "string"
                    }
                },
                "required": [
                    "REGEX"
                ]
            }
        ]
    },
    "type": "array"
}
```
