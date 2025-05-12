## General symbols

| Name | Text |
| ---- | ---- |
| [Clear](symbols/Clear.md) | Remove all persistent events from the database. |
| [ClearLocalizations](symbols/ClearLocalizations.md) | Remove all localizations from the database. |
| [Diagnostics](symbols/Diagnostics.md) | Get information about the amount of data that is currently in the database. |
| [ListEvents](symbols/ListEvents.md) | Deprecated. User the global 'ListUsers' function symbol instead. |

## General properties

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [DEFAULT_LIST_LIMIT](properties/DEFAULT_LIST_LIMIT.md) | Default limit for entry lists | This limit is used for all requests for which no other limit has been specified. |
| [MAXENTRIES](properties/MAXENTRIES.md) | Maximum number of entries | To limit the database size, the oldest database entries are permanently deleted when this limit is exceeded. |
| [MAXENTRYLENGTH](properties/MAXENTRYLENGTH.md) | Maximum length of an entry | Entries that exceed this limit will be truncated before being stored. |
| [MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT](properties/MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT.md) | Maximum count of archive files containing diagnostic messages | Server restart required. |
| [MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE](properties/MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE.md) | Maximum size of the file containing the diagnostic messages | Server restart required. |
| [MODE](properties/MODE.md) | Mode | Synchronous off mode is fast but can corrupt the database in case of a power failure. |
| [REDIRECT_DIAGNOSTICS_MESSAGES_TO_FILE](properties/REDIRECT_DIAGNOSTICS_MESSAGES_TO_FILE.md) | Redirect diagnostics messages to file | Reduces the chance that a flood of diagnostics messages will overwhelm the system. Especially useful when diagnosing problems on smaller devices. Only supported on Windows. Server restart required. |
| [VACUUM_ON_STARTUP](properties/VACUUM_ON_STARTUP.md) | Vacuum at startup | Tries to reduce database size. This might take a while on big databases. |

