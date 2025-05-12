## Allgemeine Symbole

| Name | Text |
| ---- | ---- |
| [DeleteDatabaseEntries](symbols/DeleteDatabaseEntries.de.md) | Löschen von Einträgen aus der Historize-Datenbank. Bei Bedarf Vacuum auf der Konfigurationsseite aktivieren. |
| [Diagnostics](symbols/Diagnostics.de.md) | Abrufen von Informationen über die in der Datenbank gespeicherten historisierten Daten. |
| [GetTrendLineData](symbols/GetTrendLineData.de.md) | Abrufen eines Arrays, das die Aufzeichnungszeit und den zugehörigen Datenpunkt für jedes historisierte Symbol enthält. |
| [GetTrendLineWindow](symbols/GetTrendLineWindow.de.md) | Abrufen des Fensters für ein bestimmtes TrendLineChart. |
| [HistorizeData](symbols/HistorizeData.de.md) | Abrufen der historisierten Daten. |

## Allgemeine Eigenschaften

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [commitInterval](properties/commitInterval.de.md) | Commit-Intervall | Die Zeit zwischen dem Schreiben jeder Transaktion in die Datenbank. |
| [enableBackup](properties/enableBackup.de.md) | Datenbank-Backups aktivieren | Erstellt kontinuierlich Datenbank-Backups. |
| [historizedSymbolList](properties/historizedSymbolList.de.md) | Historisierte Symbole | Liste mit allen historisierten Symbolen. |
| [inMemory](properties/inMemory.de.md) | Nicht-persistente Datenbank | Aktive Option speichert in flüchtigem RAM. Server-Neustart erforderlich. |
| [maxBackups](properties/maxBackups.de.md) | Maximale Anzahl von Datenbank-Backups | Sobald die maximale Anzahl von Backups erreicht ist, werden die ältesten Backups gelöscht. |
| [mode](properties/mode.de.md) | Modus | Die Einstellungen Synchronisation aus und Aufzeichnung im flüchtigen Speicher können die Datenbank korrumpieren. |
| [vacuumOnStartup](properties/vacuumOnStartup.de.md) | Vacuum beim Start | Versucht, die Datenbankgröße zu reduzieren. Dies kann bei großen Datenbanken eine Weile dauern. |

## Typ-Definitionen

| Name | Beschreibung |
| ---- | ------------ |
| [stringTypeArray](definitions/stringTypeArray.de.md) | Breite der X-Achse in Millisekunden. |

