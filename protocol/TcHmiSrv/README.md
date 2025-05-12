## General symbols

| Name | Text |
| ---- | ---- |
| [Diagnostics](symbols/Diagnostics.md) | Get information about the current state of the HMI server. |
| [GetSchema](symbols/GetSchema.md) | Get the schema of a specific mapped symbol. |
| [GetServerInformation](symbols/GetServerInformation.md) | Get information about the server. |
| [Heartbeat](symbols/Heartbeat.md) | A function symbol that does not do anything and does not return anything. |
| [ListDomains](symbols/ListDomains.md) | Get list of registered domains. |
| [ListFiles](symbols/ListFiles.md) | Get a list of all files in a particular directory. |
| [ListUsers](symbols/ListUsers.md) | Returns a list of all users and their permissions. |
| [LocalizeText](symbols/LocalizeText.md) | The localized text. |
| [RefreshDefinitions](symbols/RefreshDefinitions.md) | Refresh all definitions of a particular type. |
| [Restart](symbols/Restart.md) | Restart command. |
| [Shutdown](symbols/Shutdown.md) | Shutdown command. |
| [Unsubscribe](symbols/Unsubscribe.md) | Terminate a subscription. |

## Security

| Name | Text |
| ---- | ---- |
| [DefaultAuthExtension](symbols/DefaultAuthExtension.md) | Multiple authentication extensions can be used at the same time. The default authentication extension is automatically selected on the login page. |

## Configurations and filesystem

| Name | Text |
| ---- | ---- |
| [AddToConfiguration](symbols/AddToConfiguration.md) | Add variable to configuration |
| [Copy](symbols/Copy.md) | Copy a map entry. |
| [Delete](symbols/Delete.md) | Delete the given file from the containing virtual directory. If domain is set try to delete the extension file. |
| [DeleteConfiguration](symbols/DeleteConfiguration.md) | Delete configuration. |
| [Export](symbols/Export.md) | Export a specific configuration. Requires access to the '*.Config' symbol of the requested domain. |
| [GetConfiguration](symbols/GetConfiguration.md) | Get a specific configuration. Requires access to the '*.Config' symbol of the requested domain. |
| [GetFileInformation](symbols/GetFileInformation.md) | Get information of specific file. |
| [Import](symbols/Import.md) | Import data into the configuration databases. |
| [ListConfigurations](symbols/ListConfigurations.md) | List all configurations. |
| [Remove](symbols/Remove.md) | Remove array entry. |
| [RemoveFromConfiguration](symbols/RemoveFromConfiguration.md) | Remove variable from configuration |
| [Rename](symbols/Rename.md) | Rename a map entry. |
| [RenameConfiguration](symbols/RenameConfiguration.md) | Rename configuration. |
| [SetConfiguration](symbols/SetConfiguration.md) | Set configuration. |
| [Upload](symbols/Upload.md) | Upload file to server. |

## Messages and alarms

| Name | Text |
| ---- | ---- |
| [ConfirmAlarm](symbols/ConfirmAlarm.md) | Confirm the given alarm. |
| [CreateEvent](symbols/CreateEvent.md) | Create or update an event. |
| [ListEvents](symbols/ListEvents.md) | List currently active alarms. |
| [SubscribeEvents](symbols/SubscribeEvents.md) | Subscribe to events. If events occur and are allowed by the given filter they will be sent to the websocket that called this method. |
| [UnsubscribeEvents](symbols/UnsubscribeEvents.md) | Terminate an event subscription. |
| [UpdateEventsSubscription](symbols/UpdateEventsSubscription.md) | Update the subscription to events. |

## Mapped symbols

| Name | Text |
| ---- | ---- |
| [AddSymbol](symbols/AddSymbol.md) | Create a new mapped symbol. |
| [AddSymbols](symbols/AddSymbols.md) | Map some dynamic symbols automatically. |
| [GetDefinitions](symbols/GetDefinitions.md) | List all definitions of a particular type. |
| [IsSymbolOutdated](symbols/IsSymbolOutdated.md) | Compare the schema of a specific mapped symbol and the schema of the mapped part of the symbol tree. |
| [ListInternalSymbols](symbols/ListInternalSymbols.md) | Get list of internal symbols of all extensions. |
| [ListOutdatedSymbols](symbols/ListOutdatedSymbols.md) | Compare the schema of all mapped symbols with the schema of the part of the symbol tree they are mapped to. Return all mapped symbols for which these schemas differ. |
| [ListSymbolNames](symbols/ListSymbolNames.md) | List of mapped symbol names. |
| [ListSymbols](symbols/ListSymbols.md) | List all mapped symbols. |
| [RemoveUnusedDefinitions](symbols/RemoveUnusedDefinitions.md) | Removes all server definitions that are not used by any mapped symbol. |

## Users and sessions

| Name | Text |
| ---- | ---- |
| [AddOrChangeUser](symbols/AddOrChangeUser.md) | Call an authentication extension's AddUser function and subsequently edit the associated USERGROUPUSERS entry. When the 'parameters' object doesn't exist, this function only edits the USERGROUPUSERS entry. |
| [ChangeUserSettings](symbols/ChangeUserSettings.md) | Allows certain changes to the settings of the current user. Blocked for guest sessions. When the 'password' object exists, the authentication extension's ChangePassword function is called with this object as 'writeValue'. |
| [DefaultUserGroup](symbols/DefaultUserGroup.md) | Returns '__SystemUsers', the name of the default user group. |
| [ForceLogout](symbols/ForceLogout.md) | Log out a session |
| [GetCurrentUser](symbols/GetCurrentUser.md) | Return the currently active user. |
| [GetSymbolAccess](symbols/GetSymbolAccess.md) | Get symbol access with the current user. |
| [IsAuthRequired](symbols/IsAuthRequired.md) | Check if authentication is required for current endpoint. |
| [ListActiveSessions](symbols/ListActiveSessions.md) | Get a list of all active sessions and symbol subscriptions. |
| [ListUserGroups](symbols/ListUserGroups.md) | Returns the names of all configured user groups. |
| [ListUserNames](symbols/ListUserNames.md) | List of usernames. |
| [Login](symbols/Login.md) | The SessionId of the logged in user. |
| [Logout](symbols/Logout.md) | Log out the current user. |
| [RemoveUser](symbols/RemoveUser.md) | Call an authentication extension's RemoveUser function and subsequently remove the associated USERGROUPUSERS entry. |
| [SetLocale](symbols/SetLocale.md) | Change the locale of the current session. |

## General properties

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [CONFIGURATIONS](properties/CONFIGURATIONS.md) | Configurations | The names of all existing configurations. |
| [DEFAULTLOCALE](properties/DEFAULTLOCALE.md) | Default locale | Leave empty to use client locale. |
| [DEFAULTTIMEFORMATLOCALE](properties/DEFAULTTIMEFORMATLOCALE.md) | Default time locale | Leave empty to use client locale. |
| [DEFAULTTIMEZONE](properties/DEFAULTTIMEZONE.md) | Default timezone | Leave empty to use client timezone. |
| [EXTENSIONS](properties/EXTENSIONS.md) | Extensions | Server extensions are used to integrate additional functionality into the server. |
| [FILES](properties/FILES.md) | Files | Special handling and permissions for specific files or directories. |
| [FILESREGEX](properties/FILESREGEX.md) | Regular expressions for files | Special handling and permissions for specific files or directories that match the given regular expression. |
| [PROJECTNAME](properties/PROJECTNAME.md) | Project name | The name of the HMI project. |
| [PROJECTVERSION](properties/PROJECTVERSION.md) | Project version | This is the version of the HMI project that has been published to this server. |
| [REMOTESERVERS](properties/REMOTESERVERS.md) | Remote server | Connections to other HMI servers. The mapped symbols of remote servers can be used like symbols from extensions of the current server. |
| [REMOTESERVERS_CERTIFICATES](properties/REMOTESERVERS_CERTIFICATES.md) | Allowed certificates for remote servers | Certificates of the remote servers. |
| [REQUIREAUTH](properties/REQUIREAUTH.md) | Authentication required | Authentication should only be disabled on private networks. |
| [USERGROUPS](properties/USERGROUPS.md) | User groups | User groups have access permissions to specific symbols and files. Permissions are assigned to users based on user groups they are a member of. |
| [USERGROUPUSERS](properties/USERGROUPUSERS.md) | Members of user groups | The account settings and group memberships of all users from all authentication extensions. |
| [VIRTUALDIRECTORIES](properties/VIRTUALDIRECTORIES.md) | Virtual directories | Virtual directories are used to specify which folders paths on the file system should be served by the web server. |

## security

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [ALLOW_REMOTE_ADMIN](properties/ALLOW_REMOTE_ADMIN.md) | Admin remote access | The __SystemAdministrator is allowed to log in from a remote endpoint. If disabled, the __SystemAdministrator can only log in from the local machine. |
| [AUTO_LOGINUSER](properties/AUTO_LOGINUSER.md) | Automatic login | The user account that is configured here is logged in automatically when a new session is opened. |
| [AUTO_LOGOFF](properties/AUTO_LOGOFF.md) | Auto logoff | Can be overridden for individual user accounts. This value is used when no other value is specified for the current user. |
| [CERTIFICATE](properties/CERTIFICATE.md) | Certificate | PEM or PFX formatted certificate. |
| [CERTIFICATEEXPIRATION](properties/CERTIFICATEEXPIRATION.md) | Duration for default certificate | Shorter validity durations limit the damage from key compromise and mis-issuance. Stolen keys and mis-issued certificates are valid for a shorter period of time. |
| [CLIENTCERTIFICATES](properties/CLIENTCERTIFICATES.md) | Approved client certificates | Client certificates in this list can access the server. You can also link certificates to user groups and use them as an alternative login mechanism. |
| [DEFAULTAUTHEXTENSION](properties/DEFAULTAUTHEXTENSION.md) | Default authentication extension | Multiple authentication extensions can be used at the same time. The default authentication extension is automatically selected on the login page. |
| [KEY](properties/KEY.md) | Key | This key is used to decrypt the certificate. |
| [KEYPASSWORD](properties/KEYPASSWORD.md) | Key password | Password used to decrypt the private key or pfx file. If the certificate does not require a password, this field can be empty. |
| [REQUIRE_CLIENT_CERTIFICATE](properties/REQUIRE_CLIENT_CERTIFICATE.md) | Require client certificate | A client certificate is required to establish an HTTPS connection |
| [SAMESITE_ATTRIBUTE](properties/SAMESITE_ATTRIBUTE.md) | SameSite attribute | Specifies whether cookies should be sent for cross-page requests. |
| [SELFSIGNEDROOTCA](properties/SELFSIGNEDROOTCA.md) | Self-signed root certificate | This certificate is used to create self-signed server certificates. |
| [SELFSIGNEDROOTCAKEY](properties/SELFSIGNEDROOTCAKEY.md) | Self-signed root certificate key | This key is used to decrypt the root certificate. |
| [SHOW_MAINTENANCE_MODE](properties/SHOW_MAINTENANCE_MODE.md) | Show maintenance mode | The login page can be used to enter the maintenance mode. If this setting is false /LoginMaintenance can be used instead. Requires a user in the __SystemMaintenanceUsers group. |
| [TEMPDH](properties/TEMPDH.md) | TempDH | Custom parameters for the Diffie-Hellman (DH) key-exchange. |
| [USERSELECTTYPE](properties/USERSELECTTYPE.md) | Select user by | If there are only a few user accounts, selecting the user account using a list box can simplify the login process. |

## advanced

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [BASE_HMI_URL](properties/BASE_HMI_URL.md) | HMI-URL | This URL is linked on the configuration page |
| [CHECKSUMENABLED](properties/CHECKSUMENABLED.md) | Checksum enabled | Checksum of uploaded files will be validated during publishing. |
| [CHUNKSIZE](properties/CHUNKSIZE.md) | Size of chunk packet | Downloaded files will be split into chunks of this size. |
| [CUSTOM_CSS](properties/CUSTOM_CSS.md) | Custom CSS | Custom CSS for login and error pages |
| [DEFAULTEVENTEXTENSION](properties/DEFAULTEVENTEXTENSION.md) | Default logging extension | When the 'ListEvents' function symbol is called, the events are requested from the default event extension. |
| [DIAGNOSTICS_DOMAINS](properties/DIAGNOSTICS_DOMAINS.md) | Log diagnostics data for domains | Logging diagnostics data are useful to diagnose problems but they have a negative impact on performance. |
| [DISABLED_CONFIGURATION_HINTS](properties/DISABLED_CONFIGURATION_HINTS.md) | Disabled configuration hints | Hints which should not be shown anymore. |
| [FLOODPROTECTION](properties/FLOODPROTECTION.md) | Flood protection | Allowed WebSocket requests per client IP per second. |
| [FLOODPROTECTION_LOG_INTERVAL](properties/FLOODPROTECTION_LOG_INTERVAL.md) | Flood protection log interval | Time to wait before creating the next 'request failed' log entry. |
| [HTTP_FLOODPROTECTION](properties/HTTP_FLOODPROTECTION.md) | Flood protection HTTP | Allowed HTTP requests per client IP per second per URI. |
| [INITTIMEOUT](properties/INITTIMEOUT.md) | Init timeout | It should not take longer than this to initialize a server extension. |
| [MAXCONNECTIONSPERCLIENT](properties/MAXCONNECTIONSPERCLIENT.md) | Maximum connections per client | Keep in mind that web browsers might open multiple simultaneous connections to the same server to achieve faster load times. |
| [MAXHTTPHEADERSIZE](properties/MAXHTTPHEADERSIZE.md) | Maximum size of HTTP header | Requests with HTTP headers that are larger than this limit will be rejected by the web server. |
| [MAXREQUESTSIZE](properties/MAXREQUESTSIZE.md) | Maximum request size | Requests that are larger than this limit will be rejected by the web server. |
| [MAXSESSIONS](properties/MAXSESSIONS.md) | Maximum number of connections | Maximum number of concurrent connections. |
| [SHOW_CONFIGURATION_HINTS](properties/SHOW_CONFIGURATION_HINTS.md) | Show configuration hints | Configuration hints inform about problematic settings or combinations of settings in the configurations of the server or server extensions. |
| [SHUTDOWNTIMEOUT](properties/SHUTDOWNTIMEOUT.md) | Timeout for unloading extensions | It should not take longer than this to unload a server extension. |
| [SYMBOL_COMPLEXITY_LIMIT](properties/SYMBOL_COMPLEXITY_LIMIT.md) | Symbol complexity limit | Defines how complex a schema may be when mapping a symbol. The number of sub-symbols is counted |
| [THREADPOOLSIZE](properties/THREADPOOLSIZE.md) | Size of thread pool | Server restart required. |
| [UPLOADTIMEOUT](properties/UPLOADTIMEOUT.md) | Upload timeout | Upload requests will be rejected if they do not succeed after this duration. |
| [USEINT64STRING](properties/USEINT64STRING.md) | Use int64 string format | Transmit int64 as string and not as base64 |
| [VIDEOSEGMENTSIZE](properties/VIDEOSEGMENTSIZE.md) | Size of video segments | HTTP range requests (streamed videos) will be split in chunks of this size. |

## webserver

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [CACHEENABLED](properties/CACHEENABLED.md) | Enable cache | If enabled, the web-server stores frequently requested data such as web pages, images, and similar media content in RAM to improve response times. |
| [CACHEMAXAGE](properties/CACHEMAXAGE.md) | Cache max age | Server restart required. |
| [CACHEMAXENTRYSIZE](properties/CACHEMAXENTRYSIZE.md) | Cache max entry size | Server restart required. |
| [CACHEMAXSIZE](properties/CACHEMAXSIZE.md) | Cache max size | Server restart required. |
| [CLIENTPRIORITYLIST](properties/CLIENTPRIORITYLIST.md) | Client priority list | IP addresses of preferred clients. If the client limit is reached these clients will be able to connect and clients which are not in this list will be disconnected. |
| [CLIENT_CACHE_MAX_AGE](properties/CLIENT_CACHE_MAX_AGE.md) | Client-cache max age | Defines how long server responses may be cached. |
| [COOKIEEXPIRATIONDATE](properties/COOKIEEXPIRATIONDATE.md) | Cookie expiration date | The server uses cookies to store session IDs. Make sure that the cookie expiration date and the automatic logout duration are not in conflict. |
| [DEFAULTDOCUMENT](properties/DEFAULTDOCUMENT.md) | Default document | This default page is served when a web client requests a URL that points to a directory structure instead of an actual web page within the directory structure. |
| [DEFLATECOMPRESSIONLEVEL](properties/DEFLATECOMPRESSIONLEVEL.md) | GZIP compression level | GZIP compression is used by the server and web clients to improve transfer speed and bandwidth utilization. |
| [DISCOVERY](properties/DISCOVERY.md) | SSDP discovery | Changes will become active after a server restart |
| [ENDPOINTS](properties/ENDPOINTS.md) | Endpoints | IPv4 and IPv6 endpoints are supported. Only HTTPS endpoints should be enabled for remote access. Use the wildcard addresses '0.0.0.0' and '[::]' to accept remote connections on all network interfaces. |
| [ETAGENABLED](properties/ETAGENABLED.md) | Enable ETAG | The entity tag HTTP header is an identifier for a specific version of a resource. |
| [GLOBALHTTPHEADERS](properties/GLOBALHTTPHEADERS.md) | Global HTTP headers | These headers will be added to all HTTP responses. |
| [GZIPENABLED](properties/GZIPENABLED.md) | Enable GZIP | GZIP compression is used by the server and web clients to improve transfer speed and bandwidth utilization. |
| [GZIPMINSIZE](properties/GZIPMINSIZE.md) | GZIP minimum size | Prevents small data from getting zipped. |
| [KEEP_ALIVE](properties/KEEP_ALIVE.md) | Keep alive | Timer for persistent connections. |
| [PERMESSAGEDEFLATEENABLED](properties/PERMESSAGEDEFLATEENABLED.md) | Enable PerMessageDeflate | Try to enable compression for all WebSocket requests. Compression is not enabled for clients that don't support it. |
| [SESSIONSTORAGE](properties/SESSIONSTORAGE.md) | Saved sessions | Sessions are saved here so that they are still valid after a server restart. |
| [SOCKET_TIMEOUT](properties/SOCKET_TIMEOUT.md) | Socket timeout | Timeout for incomplete message body. |

## symbols

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [DEFINITIONS](properties/DEFINITIONS.md) | Definitions | Storage for JSON schema definitions. |
| [SYMBOLS](properties/SYMBOLS.md) | Mapped symbols | Mapped symbols are used to grant access to internal symbols of a domain. |

## Type definitions

| Name | Description |
| ---- | ----------- |
| [accessEnum](definitions/accessEnum.md) | Access level |
| [adsRoute](definitions/adsRoute.md) | ADS route |
| [alarm](definitions/alarm.md) | Alarm |
| [alarmState](definitions/alarmState.md) | Alarm state |
| [confirmationState](definitions/confirmationState.md) | Alarm confirmation state |
| [event](definitions/event.md) | Event |
| [eventFilter](definitions/eventFilter.md) | Event filter |
| [eventType](definitions/eventType.md) | Event type |
| [fileInfo](definitions/fileInfo.md) | File information |
| [fileSettings](definitions/fileSettings.md) | File settings |
| [filter](definitions/filter.md) | Filter |
| [message](definitions/message.md) | Message |
| [nullableDateTime](definitions/nullableDateTime.md) | Nullable datetime |
| [severity](definitions/severity.md) | Severity |
| [symbol](definitions/symbol.md) | Symbol |
| [threadPoolSize](definitions/threadPoolSize.md) | Thread pool size |
| [timing](definitions/timing.md) | Timing |
| [userGroups](definitions/userGroups.md) | User groups |
| [userLocale](definitions/userLocale.md) | User locale |
| [userTimeZone](definitions/userTimeZone.md) | User timezone |
| [valueType](definitions/valueType.md) | Value type |

