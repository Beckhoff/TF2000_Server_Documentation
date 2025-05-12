## Allgemeine Symbole

| Name | Text |
| ---- | ---- |
| [AddUser](symbols/AddUser.de.md) | Add or update user. |
| [ChangePassword](symbols/ChangePassword.de.md) | Change the password of the current user. |
| [Disable2FA](symbols/Disable2FA.de.md) | Disable 2FA for the current user |
| [DisableUser](symbols/DisableUser.de.md) | Disable a user. |
| [Enable2FA](symbols/Enable2FA.de.md) | Enable 2FA for the current user and add the secret |
| [EnableUser](symbols/EnableUser.de.md) | Enable a user. |
| [Get2FAStatus](symbols/Get2FAStatus.de.md) | Get the 2FA-Status of the current user or the specified user |
| [GetComplexityRules](symbols/GetComplexityRules.de.md) | Get a list of all enabled password complexity rules. All regular expressions use the ECMAScript syntax. |
| [ListDisabledUsers](symbols/ListDisabledUsers.de.md) | Get a list of all disabled users that are configured in this authentication extension. |
| [ListUsers](symbols/ListUsers.de.md) | Get a list of all users that are configured in this authentication extension. |
| [RemoveUser](symbols/RemoveUser.de.md) | Remove a user. |
| [RenameUser](symbols/RenameUser.de.md) | Rename a user. |
| [Reset2FA](symbols/Reset2FA.de.md) | Reset the 2FA-Secret of the specified user |

## Allgemeine Eigenschaften

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [ENABLE_TWO_FACTOR_AUTHENTICATION](properties/ENABLE_TWO_FACTOR_AUTHENTICATION.de.md) | Zwei-Faktor-Authentifizierung erfordern | Aktiviere Zwei-Faktor-Authentifizierung (2FA) mit zeitbasierten Einmalpasswörtern (TOTPs). Benutzer müssen 2FA bei ihrem nächsten Login einrichten. |
| [PASSWORD_BLACKLIST](properties/PASSWORD_BLACKLIST.de.md) | Passwort-Blacklist | Eine Liste von Passwörtern, welche Benutzer nicht wählen können. Ein Passwort pro Zeile. |
| [PASSWORD_ENABLE_AGING](properties/PASSWORD_ENABLE_AGING.de.md) | Passwortalterung aktiv | Wenn aktiviert, muss der Benutzer nach dem angegebenen Zeitraum ein neues Passwort wählen. |
| [PASSWORD_FORCE_COMPLEX](properties/PASSWORD_FORCE_COMPLEX.de.md) | Regeln für die Passwortkomplexität | Gemäß der GMP-Regeln muss ein Passwort Großbuchstaben, Kleinbuchstaben, Sonderzeichen und Zahlen enthalten. |
| [PASSWORD_MAXIMUM_AGE](properties/PASSWORD_MAXIMUM_AGE.de.md) | Maximales Passwortalter | Der Zeitraum, in dem ein Benutzer das Passwort ändern muss. |
| [PASSWORD_MINIMUM_LENGTH](properties/PASSWORD_MINIMUM_LENGTH.de.md) | Minimale Passwortlänge | Die Mindestlänge der Passwörter, die ein Benutzer wählen kann. |
| [USERS](properties/USERS.de.md) | Benutzer | Enthält Informationen über alle verwalteten Benutzerkonten. |

