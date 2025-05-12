## Allgemeine Symbole

| Name | Text |
| ---- | ---- |
| [Clear](symbols/Clear.de.md) | Remove all persistent events from the database. |
| [ClearLocalizations](symbols/ClearLocalizations.de.md) | Remove all localizations from the database. |
| [Diagnostics](symbols/Diagnostics.de.md) | Get information about the amount of data that is currently in the database. |
| [ListEvents](symbols/ListEvents.de.md) | Deprecated. User the global 'ListUsers' function symbol instead. |

## Allgemeine Eigenschaften

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [DEFAULT_LIST_LIMIT](properties/DEFAULT_LIST_LIMIT.de.md) | Standardlimit für Eintragslisten | Dieses Limit wird für alle Anfragen verwendet, für die kein anderes Limit angegeben wurde. |
| [MAXENTRIES](properties/MAXENTRIES.de.md) | Maximale Anzahl von Einträgen | Um die Datenbankgröße zu begrenzen, werden die ältesten Datenbankeinträge unwiderruflich gelöscht, wenn dieses Limit überschritten wird. |
| [MAXENTRYLENGTH](properties/MAXENTRYLENGTH.de.md) | Maximale Länge eines Eintrags | Einträge, die dieses Limit überschreiten, werden vor dem Speichern gekürzt. |
| [MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT](properties/MAX_DIAGNOSTICS_ARCHIVE_FILE_COUNT.de.md) | Maximale Anzahl der Archivdateien, die Diagnosemeldungen enthalten | Server-Neustart erforderlich. |
| [MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE](properties/MAX_DIAGNOSTICS_MESSAGES_FILE_SIZE.de.md) | Maximale Größe der Datei, die die Diagnosemeldungen enthält | Server-Neustart erforderlich. |
| [MODE](properties/MODE.de.md) | Modus | Synchronisation aus ist schneller, kann aber im Fall eines Stromausfalls die Datenbank korrumpieren. |
| [REDIRECT_DIAGNOSTICS_MESSAGES_TO_FILE](properties/REDIRECT_DIAGNOSTICS_MESSAGES_TO_FILE.de.md) | Diagnosemeldungen in eine Datei umleiten | Verringert die Wahrscheinlichkeit, dass eine Flut von Diagnosemeldungen das System überfordert. Besonders nützlich bei der Diagnose von Problemen auf kleineren Geräten. Diese Funktion wird nur auf Windows unterstützt. Server-Neustart erforderlich. |
| [VACUUM_ON_STARTUP](properties/VACUUM_ON_STARTUP.de.md) | Vacuum beim Start | Versucht, die Datenbankgröße zu reduzieren. Dies kann bei großen Datenbanken sehr lange dauern. |

