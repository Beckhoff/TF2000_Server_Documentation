## Allgemeine Symbole

| Name | Text |
| ---- | ---- |
| [Diagnostics](symbols/Diagnostics.de.md) | Get information about the current state of the HMI server. |
| [GetSchema](symbols/GetSchema.de.md) | Get the schema of a specific mapped symbol. |
| [GetServerInformation](symbols/GetServerInformation.de.md) | Get information about the server. |
| [Heartbeat](symbols/Heartbeat.de.md) | A function symbol that does not do anything and does not return anything. |
| [ListDomains](symbols/ListDomains.de.md) | Get list of registered domains. |
| [ListFiles](symbols/ListFiles.de.md) | Get a list of all files in a particular directory. |
| [ListUsers](symbols/ListUsers.de.md) | Returns a list of all users and their permissions. |
| [LocalizeText](symbols/LocalizeText.de.md) | The localized text. |
| [RefreshDefinitions](symbols/RefreshDefinitions.de.md) | Refresh all definitions of a particular type. |
| [Restart](symbols/Restart.de.md) | Restart command. |
| [Shutdown](symbols/Shutdown.de.md) | Shutdown command. |
| [Unsubscribe](symbols/Unsubscribe.de.md) | Terminate a subscription. |

## Sicherheit

| Name | Text |
| ---- | ---- |
| [DefaultAuthExtension](symbols/DefaultAuthExtension.de.md) | Multiple authentication extensions can be used at the same time. The default authentication extension is automatically selected on the login page. |

## Konfigurationen und Dateisystem

| Name | Text |
| ---- | ---- |
| [AddToConfiguration](symbols/AddToConfiguration.de.md) | Add variable to configuration |
| [Copy](symbols/Copy.de.md) | Copy a map entry. |
| [Delete](symbols/Delete.de.md) | Delete the given file from the containing virtual directory. If domain is set try to delete the extension file. |
| [DeleteConfiguration](symbols/DeleteConfiguration.de.md) | Delete configuration. |
| [Export](symbols/Export.de.md) | Export a specific configuration. Requires access to the '*.Config' symbol of the requested domain. |
| [GetConfiguration](symbols/GetConfiguration.de.md) | Get a specific configuration. Requires access to the '*.Config' symbol of the requested domain. |
| [GetFileInformation](symbols/GetFileInformation.de.md) | Get information of specific file. |
| [Import](symbols/Import.de.md) | Import data into the configuration databases. |
| [ListConfigurations](symbols/ListConfigurations.de.md) | List all configurations. |
| [Remove](symbols/Remove.de.md) | Remove array entry. |
| [RemoveFromConfiguration](symbols/RemoveFromConfiguration.de.md) | Remove variable from configuration |
| [Rename](symbols/Rename.de.md) | Rename a map entry. |
| [RenameConfiguration](symbols/RenameConfiguration.de.md) | Rename configuration. |
| [SetConfiguration](symbols/SetConfiguration.de.md) | Set configuration. |
| [Upload](symbols/Upload.de.md) | Upload file to server. |

## Nachrichten und Alarme

| Name | Text |
| ---- | ---- |
| [ConfirmAlarm](symbols/ConfirmAlarm.de.md) | Confirm the given alarm. |
| [CreateEvent](symbols/CreateEvent.de.md) | Create or update an event. |
| [ListEvents](symbols/ListEvents.de.md) | List currently active alarms. |
| [SubscribeEvents](symbols/SubscribeEvents.de.md) | Subscribe to events. If events occur and are allowed by the given filter they will be sent to the websocket that called this method. |
| [UnsubscribeEvents](symbols/UnsubscribeEvents.de.md) | Terminate an event subscription. |
| [UpdateEventsSubscription](symbols/UpdateEventsSubscription.de.md) | Update the subscription to events. |

## Symbol-Mappings

| Name | Text |
| ---- | ---- |
| [AddSymbol](symbols/AddSymbol.de.md) | Create a new mapped symbol. |
| [AddSymbols](symbols/AddSymbols.de.md) | Map some dynamic symbols automatically. |
| [GetDefinitions](symbols/GetDefinitions.de.md) | List all definitions of a particular type. |
| [IsSymbolOutdated](symbols/IsSymbolOutdated.de.md) | Compare the schema of a specific mapped symbol and the schema of the mapped part of the symbol tree. |
| [ListInternalSymbols](symbols/ListInternalSymbols.de.md) | Get list of internal symbols of all extensions. |
| [ListOutdatedSymbols](symbols/ListOutdatedSymbols.de.md) | Compare the schema of all mapped symbols with the schema of the part of the symbol tree they are mapped to. Return all mapped symbols for which these schemas differ. |
| [ListSymbolNames](symbols/ListSymbolNames.de.md) | List of mapped symbol names. |
| [ListSymbols](symbols/ListSymbols.de.md) | List all mapped symbols. |
| [RemoveUnusedDefinitions](symbols/RemoveUnusedDefinitions.de.md) | Removes all server definitions that are not used by any mapped symbol. |

## Benutzer und Sitzungen

| Name | Text |
| ---- | ---- |
| [AddOrChangeUser](symbols/AddOrChangeUser.de.md) | Call an authentication extension's AddUser function and subsequently edit the associated USERGROUPUSERS entry. When the 'parameters' object doesn't exist, this function only edits the USERGROUPUSERS entry. |
| [ChangeUserSettings](symbols/ChangeUserSettings.de.md) | Allows certain changes to the settings of the current user. Blocked for guest sessions. When the 'password' object exists, the authentication extension's ChangePassword function is called with this object as 'writeValue'. |
| [DefaultUserGroup](symbols/DefaultUserGroup.de.md) | Returns '__SystemUsers', the name of the default user group. |
| [ForceLogout](symbols/ForceLogout.de.md) | Log out a session |
| [GetCurrentUser](symbols/GetCurrentUser.de.md) | Return the currently active user. |
| [GetSymbolAccess](symbols/GetSymbolAccess.de.md) | Get symbol access with the current user. |
| [IsAuthRequired](symbols/IsAuthRequired.de.md) | Check if authentication is required for current endpoint. |
| [ListActiveSessions](symbols/ListActiveSessions.de.md) | Get a list of all active sessions and symbol subscriptions. |
| [ListUserGroups](symbols/ListUserGroups.de.md) | Returns the names of all configured user groups. |
| [ListUserNames](symbols/ListUserNames.de.md) | List of usernames. |
| [Login](symbols/Login.de.md) | The SessionId of the logged in user. |
| [Logout](symbols/Logout.de.md) | Log out the current user. |
| [RemoveUser](symbols/RemoveUser.de.md) | Call an authentication extension's RemoveUser function and subsequently remove the associated USERGROUPUSERS entry. |
| [SetLocale](symbols/SetLocale.de.md) | Change the locale of the current session. |

## Allgemeine Eigenschaften

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [CONFIGURATIONS](properties/CONFIGURATIONS.de.md) | Konfigurationen | Die Namen aller vorhandenen Konfigurationen. |
| [DEFAULTLOCALE](properties/DEFAULTLOCALE.de.md) | Standard-Lokalisierung | Leer lassen, um die Client-Spracheinstellung zu verwenden. |
| [DEFAULTTIMEFORMATLOCALE](properties/DEFAULTTIMEFORMATLOCALE.de.md) | Standard-Zeit-Lokalisierung | Leer lassen, um die Client-Spracheinstellung zu verwenden. |
| [DEFAULTTIMEZONE](properties/DEFAULTTIMEZONE.de.md) | Standard-Zeitzone | Leer lassen, um die Client-Zeitzoneneinstellung zu verwenden. |
| [EXTENSIONS](properties/EXTENSIONS.de.md) | Erweiterungen | Server-Erweiterungen werden verwendet, um zusätzliche Funktionen in den Server zu integrieren. |
| [FILES](properties/FILES.de.md) | Dateien | Spezielle Einstellungen und Berechtigungen für bestimmte Dateien oder Verzeichnisse. |
| [FILESREGEX](properties/FILESREGEX.de.md) | Reguläre Ausdrücke für Dateien | Spezielle Einstellungen und Berechtigungen für bestimmte Dateien oder Verzeichnisse die auf den angegebenen regulären Ausdruck zutreffen. |
| [PROJECTNAME](properties/PROJECTNAME.de.md) | Projektname | Der Name des HMI-Projektes. |
| [PROJECTVERSION](properties/PROJECTVERSION.de.md) | Projektversion | Die Version des zuletzt hochgeladenen HMI-Projekts. |
| [REMOTESERVERS](properties/REMOTESERVERS.de.md) | Remote-Server | Verbindungen zu anderen HMI-Servern. Die Symbol-Mappings von Remote-Servern können wie Symbole von Erweiterungen des aktuellen Servers verwendet werden. |
| [REMOTESERVERS_CERTIFICATES](properties/REMOTESERVERS_CERTIFICATES.de.md) | Erlaubte Zertifikate für Remote-Server | Zertifikate der Remote-Server. |
| [REQUIREAUTH](properties/REQUIREAUTH.de.md) | Authentifizierung erforderlich | Authentifizierung sollte nur in privaten Netzwerken deaktiviert werden. |
| [USERGROUPS](properties/USERGROUPS.de.md) | Nutzergruppen | Benutzergruppen haben Zugriffsberechtigungen auf bestimmte Symbole und Dateien. Die Berechtigungen werden den Benutzern auf der Grundlage der Benutzergruppen, denen sie angehören, zugewiesen. |
| [USERGROUPUSERS](properties/USERGROUPUSERS.de.md) | Gruppenmitglieder | Die Account-Einstellungen und Gruppenmitgliedschaften aller Benutzer aller Authentifizierungserweiterungen. |
| [VIRTUALDIRECTORIES](properties/VIRTUALDIRECTORIES.de.md) | Virtuelle Verzeichnisse | Virtuelle Verzeichnisse werden verwendet, um anzugeben, welche Ordnerpfade des Dateisystems über den Webserver bereitgestellt werden sollen. |

## security

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [ALLOW_REMOTE_ADMIN](properties/ALLOW_REMOTE_ADMIN.de.md) | Admin-Remote-Zugriff | Der __SystemAdministrator darf sich von einem Remote-Endpoint aus anmelden. Falls deaktiviert, kann sich der __SystemAdministrator nur auf der lokalen Maschine anmelden. |
| [AUTO_LOGINUSER](properties/AUTO_LOGINUSER.de.md) | Automatischer Login | Der hier konfigurierte Benutzer wird automatisch eingeloggt, wenn eine neue Sitzung eröffnet wird. |
| [AUTO_LOGOFF](properties/AUTO_LOGOFF.de.md) | Automatische Abmeldung | Kann für einzelne Benutzerkonten überschrieben werden. Dieser Wert wird verwendet, wenn für den aktuellen Benutzer kein anderer Wert angegeben ist. Achten Sie darauf, dass das Cookie-Ablaufdatum und die Zeit der automatischen Abmeldung nicht im Widerspruch zueinander stehen. |
| [CERTIFICATE](properties/CERTIFICATE.de.md) | Zertifikat | Zertifikat im PEM- oder PFX-Format. |
| [CERTIFICATEEXPIRATION](properties/CERTIFICATEEXPIRATION.de.md) | Gültigkeitsdauer für Zertifikate | Kürzere Gültigkeitsdauern begrenzen den Schaden durch Schlüsselkompromittierung und Falschausstellungen. Gestohlene Schlüssel und falsch ausgestellte Zertifikate sind für einen kürzeren Zeitraum gültig. |
| [CLIENTCERTIFICATES](properties/CLIENTCERTIFICATES.de.md) | Client-Zertifikate | Client-Zertifikate in dieser Liste können auf den Server zugreifen. Sie können Zertifikate auch mit Benutzergruppen verknüpfen und diese als alternativen Anmeldemechanismus verwenden. |
| [DEFAULTAUTHEXTENSION](properties/DEFAULTAUTHEXTENSION.de.md) | Standard-Authentifizierungs-Erweiterung | Es können mehrere Authentifizierungserweiterungen gleichzeitig verwendet werden. Die Standard-Authentifizierungserweiterung wird standardmäßig auf der Login-Seite ausgewählt. |
| [KEY](properties/KEY.de.md) | Schlüssel | Dieser Schlüssel wird zur Entschlüsselung des Zertifikats verwendet. Bei Zertifikation im PFX-Format kann dieses Feld leer bleiben. |
| [KEYPASSWORD](properties/KEYPASSWORD.de.md) | Schlüssel-Passwort | Passwort für die Dekodierung des privaten Schlüssels oder der PFX-Datei. Wenn das Zertifikat kein Passwort benötigt, kann dieses Feld leer bleiben. |
| [REQUIRE_CLIENT_CERTIFICATE](properties/REQUIRE_CLIENT_CERTIFICATE.de.md) | Client-Zertifikat erforderlich | Ein Client-Zertifikat ist erforderlich, um eine HTTPS-Verbindung herzustellen |
| [SAMESITE_ATTRIBUTE](properties/SAMESITE_ATTRIBUTE.de.md) | SameSite-Attribut | Definiert, ob Cookies bei Cross-Site-Requests mitgesendet werden sollen. |
| [SELFSIGNEDROOTCA](properties/SELFSIGNEDROOTCA.de.md) | Selbstsigniertes Root-Zertifikat | Dieses Zertifikat wird verwendet, um self-signed Server-Zertifikate zu erstellen. |
| [SELFSIGNEDROOTCAKEY](properties/SELFSIGNEDROOTCAKEY.de.md) | Selbstsignierter Root-Zertifikat-Schlüssel | Dieser Schlüssel wird zur Entschlüsselung des Root-Zertifikats verwendet. |
| [SHOW_MAINTENANCE_MODE](properties/SHOW_MAINTENANCE_MODE.de.md) | Wartungsmodus auf Login-Seite anzeigen | Auf der Login-Seite kann der Wartungsmodus aktiviert werden. Falls deaktiviert kann man über /LoginMaintenance weiterhin in den Wartungsmodus wechseln. Benötigt einen Benutzer in der __SystemMaintenanceUsers-Gruppe. |
| [TEMPDH](properties/TEMPDH.de.md) | TempDH | Benutzerdefinierte Parameter für den Diffie-Hellman (DH)-Schlüsselaustausch. |
| [USERSELECTTYPE](properties/USERSELECTTYPE.de.md) | Wähle Nutzer anhand von | Wenn es nur wenige Benutzerkonten gibt, kann die Auswahl des Benutzerkontos über ein Listbox den Anmeldevorgang vereinfachen. |

## advanced

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [BASE_HMI_URL](properties/BASE_HMI_URL.de.md) | HMI-URL | Diese URL wird auf der Konfigurationsseite verlinkt |
| [CHECKSUMENABLED](properties/CHECKSUMENABLED.de.md) | Prüfsumme aktiviert | Beim Publish-Prozess wird die Prüfsumme der Dateien validiert |
| [CHUNKSIZE](properties/CHUNKSIZE.de.md) | Größe eines Chunk-Pakets | Beim Herunterladen werden Dateien in Chunks dieser Größe gesendet. |
| [CUSTOM_CSS](properties/CUSTOM_CSS.de.md) | Benutzerdefiniertes CSS | Benutzerdefiniertes CSS für Fehler- und Loginseiten |
| [DEFAULTEVENTEXTENSION](properties/DEFAULTEVENTEXTENSION.de.md) | Standard-Logger-Erweiterung | Wenn das Funktionssymbol 'ListEvents' aufgerufen wird, werden die Ereignisse von der Standard-Ereigniserweiterung angefordert. |
| [DIAGNOSTICS_DOMAINS](properties/DIAGNOSTICS_DOMAINS.de.md) | Logge Diagnose-Daten für Domains | Diagnose-Nachrichten können zur Fehler-Diagnose verwendet werden. Diese Einstellung hat jedoch negative Auswirkungen auf die Performance. |
| [DISABLED_CONFIGURATION_HINTS](properties/DISABLED_CONFIGURATION_HINTS.de.md) | Deaktivierte Konfigurationshinweise | Konfigurationshinweise, die nicht mehr gezeigt werden sollen. |
| [FLOODPROTECTION](properties/FLOODPROTECTION.de.md) | Flood protection | Erlaubte WebSocket- und HTTP-Anfragen pro Client IP pro Sekunde |
| [FLOODPROTECTION_LOG_INTERVAL](properties/FLOODPROTECTION_LOG_INTERVAL.de.md) | Flood protection Benachrichtigungsintervall | Zeit, die gewartet wird, bevor der nächste 'Anfrage fehlgeschlagen' Log-Eintrag erstellt werden soll. |
| [HTTP_FLOODPROTECTION](properties/HTTP_FLOODPROTECTION.de.md) | Flood protection HTTP | Erlaubte HTTP-Anfragen pro Client IP pro Sekunde pro URI |
| [INITTIMEOUT](properties/INITTIMEOUT.de.md) | Timeout beim Initialisieren von Erweiterungen | Das Initialisieren einer Servererweiterung sollte nicht mehr als diese Zeit in Anspruch nehmen. |
| [MAXCONNECTIONSPERCLIENT](properties/MAXCONNECTIONSPERCLIENT.de.md) | Maximale Anzahl Verbindungen pro Client | Beachten Sie, dass Web-Browser unter Umständen mehrere Verbindungen gleichzeitige zu demselben Server öffnen, um schnellere Ladezeiten zu erreichen. |
| [MAXHTTPHEADERSIZE](properties/MAXHTTPHEADERSIZE.de.md) | Maximale Größe des HTTP-Headers | Anfragen mit HTTP-Headern, die größer sind als diese Grenze, werden vom Web-Server abgelehnt. |
| [MAXREQUESTSIZE](properties/MAXREQUESTSIZE.de.md) | Maximale Anfragegröße | Anfragen, die diesen Wert überschreiten, werden vom Web-Server abgelehnt. |
| [MAXSESSIONS](properties/MAXSESSIONS.de.md) | Maximale Anzahl an Verbindungen | Maximale Anzahl an gleichzeitigen Verbindungen. |
| [SHOW_CONFIGURATION_HINTS](properties/SHOW_CONFIGURATION_HINTS.de.md) | Konfigurationshinweise anzeigen | Konfigurationshinweise informieren über problematische Einstellungen oder Kombinationen von Einstellungen in den Konfigurationen des Servers oder der Servererweiterungen. |
| [SHUTDOWNTIMEOUT](properties/SHUTDOWNTIMEOUT.de.md) | Timeout beim Entladen von Erweiterungen | Das Entladen einer Servererweiterung sollte nicht mehr als diese Zeit in Anspruch nehmen. |
| [SYMBOL_COMPLEXITY_LIMIT](properties/SYMBOL_COMPLEXITY_LIMIT.de.md) | Limit der Symbolkomplexität | Definiert, wie komplex ein Schema beim Mappen eines Symbols sein darf. Gezählt werden dabei die Anzahl der Subsymbole. |
| [THREADPOOLSIZE](properties/THREADPOOLSIZE.de.md) | Größe des Thread-Pools | Server-Neustart erforderlich. |
| [UPLOADTIMEOUT](properties/UPLOADTIMEOUT.de.md) | Upload-Timeout | Upload-Anfragen werden abgelehnt, wenn sie nach dieser Zeitspanne nicht abgeschlossen sind. |
| [USEINT64STRING](properties/USEINT64STRING.de.md) | Int64-String-Format verwenden | Int64 nicht als Base64 sondern als String übertragen |
| [VIDEOSEGMENTSIZE](properties/VIDEOSEGMENTSIZE.de.md) | Größe eines Videosegments | HTTP-Range-Requests (Video-Streams) werden in Chunks dieser Größe aufgeteilt. |

## webserver

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [CACHEENABLED](properties/CACHEENABLED.de.md) | Cache aktiviert | Wenn diese Funktion aktiviert ist, speichert der Webserver häufig angeforderte Daten wie Webseiten, Bilder und ähnliche Medieninhalte im RAM, um die Antwortzeiten zu verbessern. |
| [CACHEMAXAGE](properties/CACHEMAXAGE.de.md) | Speicherdauer von Cache-Einträgen | Server-Neustart erforderlich. |
| [CACHEMAXENTRYSIZE](properties/CACHEMAXENTRYSIZE.de.md) | Maximale Größe Cache-Eintrag | Server-Neustart erforderlich. |
| [CACHEMAXSIZE](properties/CACHEMAXSIZE.de.md) | Maximale Cache-Größe | Server-Neustart erforderlich. |
| [CLIENTPRIORITYLIST](properties/CLIENTPRIORITYLIST.de.md) | Client-Priorisierung | IP-Adressen von priorisierten Clients. Wenn das Client-Limit erreicht ist, können diese Clients sich trotzdem verbinden, indem die Verbindung von Clients, die nicht in der Liste sind, getrennt wird. |
| [CLIENT_CACHE_MAX_AGE](properties/CLIENT_CACHE_MAX_AGE.de.md) | Speicherdauer Client-Cache | Definiert, wie lange Server-Antworten zwischengespeichert werden dürfen. |
| [COOKIEEXPIRATIONDATE](properties/COOKIEEXPIRATIONDATE.de.md) | Cookie-Ablaufdatum | Der Server verwendet Cookies, um Sitzungs-IDs zu speichern. Achten Sie darauf, dass das Cookie-Ablaufdatum und die Zeit der automatischen Abmeldung nicht im Widerspruch zueinander stehen. |
| [DEFAULTDOCUMENT](properties/DEFAULTDOCUMENT.de.md) | Standard-Dokument | Diese Standardseite wird angezeigt, wenn ein Web-Client eine URL anfordert, die auf eine Verzeichnisstruktur verweist, anstatt auf eine tatsächliche Webseite innerhalb der Verzeichnisstruktur. |
| [DEFLATECOMPRESSIONLEVEL](properties/DEFLATECOMPRESSIONLEVEL.de.md) | GZIP-Kompressionslevel | Die GZIP-Komprimierung wird vom Server und den Web-Clients verwendet, um die Übertragungsgeschwindigkeit und die Bandbreitennutzung zu verbessern. |
| [DISCOVERY](properties/DISCOVERY.de.md) | SSDP-Discovery | Änderung wird nach Server-Neustart aktiv |
| [ENDPOINTS](properties/ENDPOINTS.de.md) | Endpoints | Es werden IPv4- und IPv6-Endpunkte unterstützt. Nur HTTPS-Endpunkte sollten für den Remote-Zugriff aktiviert werden. Verwenden Sie die Wildcard-Adressen '0.0.0.0' und '[::]', um Remote-Verbindungen auf allen Netzwerkschnittstellen zu akzeptieren. |
| [ETAGENABLED](properties/ETAGENABLED.de.md) | ETAG aktiv | Der Entity-Tag-HTTP-Header ist eine Identifikationsnummer für eine bestimmte Version einer Ressource. |
| [GLOBALHTTPHEADERS](properties/GLOBALHTTPHEADERS.de.md) | Globale HTTP-Header | Diese Header werden in allen HTTP-Antworten gesetzt. |
| [GZIPENABLED](properties/GZIPENABLED.de.md) | GZIP aktiv | Die GZIP-Komprimierung wird vom Server und den Web-Clients verwendet, um die Übertragungsgeschwindigkeit und die Bandbreitennutzung zu verbessern. |
| [GZIPMINSIZE](properties/GZIPMINSIZE.de.md) | GZIP Minimale Größe | Verhindert das Komprimieren von kleinen Datenmengen. |
| [KEEP_ALIVE](properties/KEEP_ALIVE.de.md) | Keep-alive | Timer für persistente Verbindungen. |
| [PERMESSAGEDEFLATEENABLED](properties/PERMESSAGEDEFLATEENABLED.de.md) | PerMessageDeflate aktiv | Versucht, die Komprimierung für alle WebSocket-Anfragen zu aktivieren. Die Komprimierung wird für Clients, die diese Funktion nicht unterstützen, nicht aktiviert. |
| [SESSIONSTORAGE](properties/SESSIONSTORAGE.de.md) | Gespeicherte Sitzungen | Sitzungen werden hier gespeichert, damit sie nach einem Server-Neustart weiterhin gültig sind. |
| [SOCKET_TIMEOUT](properties/SOCKET_TIMEOUT.de.md) | Socket-Timeout | Timeout bei unvollständigem Nachrichtenrumpf. |

## symbols

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [DEFINITIONS](properties/DEFINITIONS.de.md) | Definitionen | Hier werden JSON-Schema-Definitionen gespeichert. |
| [SYMBOLS](properties/SYMBOLS.de.md) | Symbol-Mappings | Ein Symbol-Mapping ermöglicht den Zugriff auf interne Symbole einer Domäne. |

## Typ-Definitionen

| Name | Beschreibung |
| ---- | ------------ |
| [accessEnum](definitions/accessEnum.de.md) | Zugriffsstufe |
| [adsRoute](definitions/adsRoute.de.md) | ADS-Route |
| [alarm](definitions/alarm.de.md) | Alarm |
| [alarmState](definitions/alarmState.de.md) | Alarm-Zustand |
| [confirmationState](definitions/confirmationState.de.md) | Alarm-Quittierung |
| [event](definitions/event.de.md) | Ereignis |
| [eventFilter](definitions/eventFilter.de.md) | Ereignis-Filter |
| [eventType](definitions/eventType.de.md) | Ereignis-Typ |
| [fileInfo](definitions/fileInfo.de.md) | Dateiinformationen |
| [fileSettings](definitions/fileSettings.de.md) | Dateieinstellungen |
| [filter](definitions/filter.de.md) | Filter |
| [message](definitions/message.de.md) | Nachricht |
| [nullableDateTime](definitions/nullableDateTime.de.md) | Nullable datetime |
| [severity](definitions/severity.de.md) | Severity |
| [symbol](definitions/symbol.de.md) | Symbol |
| [threadPoolSize](definitions/threadPoolSize.de.md) | Thread-Pool-Größe |
| [timing](definitions/timing.de.md) | Timing |
| [userGroups](definitions/userGroups.de.md) | Nutzergruppen |
| [userLocale](definitions/userLocale.de.md) | Client-Locale |
| [userTimeZone](definitions/userTimeZone.de.md) | Client-Zeitzone |
| [valueType](definitions/valueType.de.md) | Datentyp |

