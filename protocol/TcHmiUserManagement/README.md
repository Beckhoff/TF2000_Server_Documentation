## General symbols

| Name | Text |
| ---- | ---- |
| [AddUser](symbols/AddUser.md) | Add or update user. |
| [ChangePassword](symbols/ChangePassword.md) | Change the password of the current user. |
| [Disable2FA](symbols/Disable2FA.md) | Disable 2FA for the current user |
| [DisableUser](symbols/DisableUser.md) | Disable a user. |
| [Enable2FA](symbols/Enable2FA.md) | Enable 2FA for the current user and add the secret |
| [EnableUser](symbols/EnableUser.md) | Enable a user. |
| [Get2FAStatus](symbols/Get2FAStatus.md) | Get the 2FA-Status of the current user or the specified user |
| [GetComplexityRules](symbols/GetComplexityRules.md) | Get a list of all enabled password complexity rules. All regular expressions use the ECMAScript syntax. |
| [ListDisabledUsers](symbols/ListDisabledUsers.md) | Get a list of all disabled users that are configured in this authentication extension. |
| [ListUsers](symbols/ListUsers.md) | Get a list of all users that are configured in this authentication extension. |
| [RemoveUser](symbols/RemoveUser.md) | Remove a user. |
| [RenameUser](symbols/RenameUser.md) | Rename a user. |
| [Reset2FA](symbols/Reset2FA.md) | Reset the 2FA-Secret of the specified user |

## General properties

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [ENABLE_TWO_FACTOR_AUTHENTICATION](properties/ENABLE_TWO_FACTOR_AUTHENTICATION.md) | Require Two-Factor Authentication | Enable Two-Factor Authentication (2FA) with Time-Based One-Time Passwords (TOTPs). Users will be required to set up 2FA during their next login. |
| [PASSWORD_BLACKLIST](properties/PASSWORD_BLACKLIST.md) | Password blacklist | A blacklist of passwords users cannot choose. One password per line. |
| [PASSWORD_ENABLE_AGING](properties/PASSWORD_ENABLE_AGING.md) | Password aging enabled | If enabled the user has to choose a new password after the given timespan. |
| [PASSWORD_FORCE_COMPLEX](properties/PASSWORD_FORCE_COMPLEX.md) | Enforce password complexity rules | According to GMP rules, a password must contain at least one uppercase character, lowercase character, special character, and numeric character. |
| [PASSWORD_MAXIMUM_AGE](properties/PASSWORD_MAXIMUM_AGE.md) | Maximum age for passwords | The period in which a user has to change the password. |
| [PASSWORD_MINIMUM_LENGTH](properties/PASSWORD_MINIMUM_LENGTH.md) | Minimum length of passwords | The minimum length of passwords a user can choose. |
| [USERS](properties/USERS.md) | Users | Contains the information about all managed user accounts. |

