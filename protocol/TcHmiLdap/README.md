## General symbols

| Name | Text |
| ---- | ---- |
| [Diagnostics](symbols/Diagnostics.md) | Get information about the connection between the HMI server and the configured LDAP server. |
| [GetAttributes](symbols/GetAttributes.md) | Get the values of the public attributes of the current user. |
| [ListNamingContexts](symbols/ListNamingContexts.md) | Get a list of the naming contexts that are hosted by the configured LDAP server. |
| [ListUsers](symbols/ListUsers.md) | Get a list of the users that are known by this authentication extension. |

## General properties

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [BASE_DN](properties/BASE_DN.md) | Base DN | Entry point for LDAP search requests. If empty, the domain components of the host are used. |
| [CASE_SENSITIVE_ATTRIBUTE_VALUE_COMPARISON](properties/CASE_SENSITIVE_ATTRIBUTE_VALUE_COMPARISON.md) | Case-sensitive comparison of attribute values | DNs and attributes are case-insensitive by default. It is possible to define an attribute as case-sensitive in the schema, but this is rare. |
| [HOST](properties/HOST.md) | Host | A hostname, a domain name, or an IP address. IPv6 is currently not supported. |
| [LDAP_OPT_REFERRALS](properties/LDAP_OPT_REFERRALS.md) | Follow referrals | Specifies whether to automatically follow referrals returned by the LDAP server. |
| [PORT](properties/PORT.md) | Port | The most common ports are 636 for TLS and 389 for unencrypted connections. |
| [SYNC_INTERVAL](properties/SYNC_INTERVAL.md) | Synchronization interval | In this interval, the groups of active sessions are synchronized with the LDAP server. Sessions of blocked users will be terminated. |
| [TIMEOUT](properties/TIMEOUT.md) | Timeout | This timeout is used for all LDAP requests, including search requests. |
| [TRUST_ALL_CERTIFICATES](properties/TRUST_ALL_CERTIFICATES.md) | Trust all certificates | If 'false', check whether the server certificate was issued by a certificate authority trusted by the operating system. |
| [USE_TLS](properties/USE_TLS.md) | Use TLS | Strongly recommended, especially when using the 'Simple' authentication mechanism. |

## authentication

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [APPEND_DOMAIN_DURING_LOGIN](properties/APPEND_DOMAIN_DURING_LOGIN.md) | Append the domain during login | For example, if the 'email' or 'userPrincipalName' is used for login, this setting can be used to automatically add the domain suffix so that it does not need to be specified at login. The extension does a case-insensitive check to find out if the domain suffix is already present. |
| [AUTHENTICATION_MECHANISM](properties/AUTHENTICATION_MECHANISM.md) | Authentication mechanism | The most common mechanism is 'Simple'. 'Digest-MD5' is recommended when TLS is unavailable. |
| [IGNORE_DOMAIN_SUFFIX_DURING_LOGIN](properties/IGNORE_DOMAIN_SUFFIX_DURING_LOGIN.md) | Ignore the domain suffix during login | Ignore everything after the first @ in the username submitted by the user. If you are, for example, using 'userPrincipalName' on Active Directory, you need to disable this setting because the userPrincipalName contains an @. |
| [USERNAME_ATTRIBUTE](properties/USERNAME_ATTRIBUTE.md) | Username attribute | Attribute used to identify the user. |
| [USER_FILTER](properties/USER_FILTER.md) | User filter | Used to search for the user entry. {input} is a placeholder replaced by what the user inputs in the login form. {username_attribute} is a placeholder replaced by the configured username attribute. |
| [USE_LDAP_SEARCH_FOR_LISTUSERS](properties/USE_LDAP_SEARCH_FOR_LISTUSERS.md) | Use LDAP search for ListUsers | Depending on the size of the directory, the search might take too long or return too many results. If disabled, the usernames are collected from the TcHmiSrv configuration. |

## integration

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [ADDED_GROUPS_CACHE](properties/ADDED_GROUPS_CACHE.md) | Cache for added user groups | This cache is needed to correctly remove user group memberships that were configured based on group mappings. |
| [BLOCK_USERS](properties/BLOCK_USERS.md) | Block specific users | Blocked users are not able to log in, even if they logged in successfully in the past. |
| [GROUP_MAPPINGS](properties/GROUP_MAPPINGS.md) | Group mappings | Set HMI user groups based on an LDAP user's attributes. |
| [VISIBLE_ATTRIBUTES](properties/VISIBLE_ATTRIBUTES.md) | Visible attributes | The names of the attributes that users can query from their LDAP directory entry. |

## bindUser

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [BIND_USER_AUTHENTICATION_MECHANISM](properties/BIND_USER_AUTHENTICATION_MECHANISM.md) | Authentication mechanism for bind user | 'None' means that there is no bind user, in which case, the bind request is done with what the user inputs in the login form. |
| [BIND_USER_DN](properties/BIND_USER_DN.md) | Bind user DN | The full DN of the admin user that is used to search for the DN of the user that is trying to sign in. This setting is ignored if the authentication mechanism is 'Anonymous', 'Kerberos-Credential-Cache', or 'None'. |
| [BIND_USER_PASSWORD](properties/BIND_USER_PASSWORD.md) | Bind user password | Encrypted before it is stored in the configuration database. Decrypted during a configuration export. |

## Type definitions

| Name | Description |
| ---- | ----------- |
| [ldapAttributeValue](definitions/ldapAttributeValue.md) |  |
| [ldapDistinguishedName](definitions/ldapDistinguishedName.md) |  |

