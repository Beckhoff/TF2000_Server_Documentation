## Allgemeine Symbole

| Name | Text |
| ---- | ---- |
| [Diagnostics](symbols/Diagnostics.de.md) | Get information about the connection between the HMI server and the configured LDAP server. |
| [GetAttributes](symbols/GetAttributes.de.md) | Get the values of the public attributes of the current user. |
| [ListNamingContexts](symbols/ListNamingContexts.de.md) | Get a list of the naming contexts that are hosted by the configured LDAP server. |
| [ListUsers](symbols/ListUsers.de.md) | Get a list of the users that are known by this authentication extension. |

## Allgemeine Eigenschaften

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [BASE_DN](properties/BASE_DN.de.md) | Basis-DN | Einstiegspunkt für LDAP-Suchanfragen. Falls leer, werden die Domain-Komponenten des Hosts verwendet. |
| [CASE_SENSITIVE_ATTRIBUTE_VALUE_COMPARISON](properties/CASE_SENSITIVE_ATTRIBUTE_VALUE_COMPARISON.de.md) | Attribute-Werte unter Berücksichtigung der Groß-/Kleinschreibung vergleichen | Bei DNs und Attributen wird standardmäßig nicht zwischen Groß- und Kleinschreibung unterschieden. Es ist möglich, diese Einstellung im LDAP-Schema des Attributs zu ändern, aber dies ist selten. |
| [HOST](properties/HOST.de.md) | Host | Ein Hostname, ein Domänenname oder eine IP-Adresse. IPv6 wird derzeit nicht unterstützt. |
| [LDAP_OPT_REFERRALS](properties/LDAP_OPT_REFERRALS.de.md) | Folge Referrals | Gibt an, ob den vom LDAP-Server zurückgegebenen Referrals automatisch gefolgt werden soll. |
| [PORT](properties/PORT.de.md) | Port | Die gängigsten Ports sind 636 für TLS und 389 für unverschlüsselte Verbindungen. |
| [SYNC_INTERVAL](properties/SYNC_INTERVAL.de.md) | Synchronisierungs-Intervall | In diesem Intervall werden die Gruppen aktiver Sitzungen mit dem LDAP-Server synchronisiert. Sitzungen gesperrter Nutzer werden beendet. |
| [TIMEOUT](properties/TIMEOUT.de.md) | Timeout | Dieses Timeout wird für alle LDAP-Anfragen, einschließlich Suchanfragen, verwendet. |
| [TRUST_ALL_CERTIFICATES](properties/TRUST_ALL_CERTIFICATES.de.md) | Allen Zertifikaten vertrauen | Falls 'false', wird überprüft, ob das Server-Zertifikat von einer Zertifizierungsstelle ausgestellt wurde, der das Betriebssystem vertraut. |
| [USE_TLS](properties/USE_TLS.de.md) | Verwende TLS | Nachdrücklich empfohlen, insbesondere bei Verwendung des Authentifizierungsmechanismus 'Simple'. |

## authentication

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [APPEND_DOMAIN_DURING_LOGIN](properties/APPEND_DOMAIN_DURING_LOGIN.de.md) | Ergänze die Domain während der Anmeldung | Wenn beispielsweise die 'email' oder 'userPrincipalName' zur Anmeldung verwendet wird, kann mit dieser Einstellung der Domain-Suffix automatisch ergänzt werden, sodass dieser bei der Anmeldung nicht angegeben werden muss. Es wird eine Prüfung ohne Berücksichtigung der Groß- und Kleinschreibung durchgeführt, um herauszufinden, ob die Domain bereits vorhanden ist. |
| [AUTHENTICATION_MECHANISM](properties/AUTHENTICATION_MECHANISM.de.md) | Authentifizierungsmechanismus | Der gängigste Mechanismus ist 'Simple'. 'Digest-MD5' wird empfohlen, wenn TLS nicht verfügbar ist. |
| [IGNORE_DOMAIN_SUFFIX_DURING_LOGIN](properties/IGNORE_DOMAIN_SUFFIX_DURING_LOGIN.de.md) | Ignoriere die Domain während der Anmeldung | Ignoriere alles, was nach dem ersten @ im bei der Anmeldung angegebenen Namen steht. Wenn beispielsweise der 'userPrincipalName' auf Active Directory verwendet wird, muss diese Einstellung deaktiviert werden, da der 'userPrincipalName' ein @ enthält. |
| [USERNAME_ATTRIBUTE](properties/USERNAME_ATTRIBUTE.de.md) | Nutzernamen-Attribut | Attribut, das zur Identifizierung des Benutzers verwendet wird. |
| [USER_FILTER](properties/USER_FILTER.de.md) | Nutzer-Filter | Wird für die Suche nach Nutzer-Einträgen verwendet. {input} wird durch das ersetzt, was der Benutzer in das Anmeldeformular eingibt. {username_attribute} ist ein Platzhalter, der durch das konfigurierte Nutzernamen-Attribut ersetzt wird. |
| [USE_LDAP_SEARCH_FOR_LISTUSERS](properties/USE_LDAP_SEARCH_FOR_LISTUSERS.de.md) | Nutze LDAP-Suchanfrage für ListUsers | Abhängig von der Größe des Verzeichnisses kann die Suche zu lange dauern oder zu viele Ergebnisse liefern. Wenn deaktiviert, werden die Benutzernamen aus der TcHmiSrv-Konfiguration gesammelt. |

## integration

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [ADDED_GROUPS_CACHE](properties/ADDED_GROUPS_CACHE.de.md) | Cache für automatisch hinzugefügte Nutzergruppen | Dieser Cache wird benötigt, um Nutzergruppen, die basierend auf Gruppen-Mappings konfiguriert werden, wieder korrekt entfernen zu können. |
| [BLOCK_USERS](properties/BLOCK_USERS.de.md) | Bestimmte Benutzer blockieren | Gesperrte Benutzer können sich nicht anmelden, selbst wenn sie sich in der Vergangenheit erfolgreich angemeldet haben. |
| [GROUP_MAPPINGS](properties/GROUP_MAPPINGS.de.md) | Gruppen-Mappings | HMI-Benutzergruppen basierend auf den Attributen eines LDAP-Benutzers setzen. |
| [VISIBLE_ATTRIBUTES](properties/VISIBLE_ATTRIBUTES.de.md) | Sichtbare Attribute | Die Namen der Attribute, die Benutzer von ihrem LDAP-Verzeichniseintrag abfragen können. |

## bindUser

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [BIND_USER_AUTHENTICATION_MECHANISM](properties/BIND_USER_AUTHENTICATION_MECHANISM.de.md) | Authentifizierungsmechanismus für den Bind-Nutzer | 'None' bedeutet, dass es keinen Bind-Nutzer gibt. In diesem Fall erfolgt die Bind-Anfrage mit dem, was der Benutzer in das Anmeldeformular eingibt. |
| [BIND_USER_DN](properties/BIND_USER_DN.de.md) | DN des Bind-Nutzers | Der vollständige DN des Bind-Nutzers, der für die Suche nach dem DN des Nutzers verwendet wird, der versucht, sich anzumelden. Diese Einstellung wird ignoriert, wenn der Authentifizierungsmechanismus 'Anonymous', 'Kerberos-Credential-Cache' oder 'None' ist. |
| [BIND_USER_PASSWORD](properties/BIND_USER_PASSWORD.de.md) | Passwort des Bind-Nutzers | Wird vor der Speicherung in der Konfigurationsdatenbank verschlüsselt. Wird beim Export der Konfiguration entschlüsselt. |

## Typ-Definitionen

| Name | Beschreibung |
| ---- | ------------ |
| [ldapAttributeValue](definitions/ldapAttributeValue.de.md) |  |
| [ldapDistinguishedName](definitions/ldapDistinguishedName.de.md) |  |

