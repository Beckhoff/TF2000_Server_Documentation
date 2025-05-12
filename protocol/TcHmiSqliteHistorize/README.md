## General symbols

| Name | Text |
| ---- | ---- |
| [DeleteDatabaseEntries](symbols/DeleteDatabaseEntries.md) | Delete records from the historize database. If necessary enable vacuum on config page. |
| [Diagnostics](symbols/Diagnostics.md) | Get information about the historized data that is stored in the database. |
| [GetTrendLineData](symbols/GetTrendLineData.md) | Get an array containing recording time and its data point for each historized symbol. |
| [GetTrendLineWindow](symbols/GetTrendLineWindow.md) | Get window for a specific TrendLineChart. |
| [HistorizeData](symbols/HistorizeData.md) | Get the historized data. |

## General properties

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [commitInterval](properties/commitInterval.md) | Commit interval | The time between writing each transaction into the database. |
| [enableBackup](properties/enableBackup.md) | Enable database backups | Creates database backups continuously. |
| [historizedSymbolList](properties/historizedSymbolList.md) | Historized symbols | List containing all historized symbols. |
| [inMemory](properties/inMemory.md) | In-memory database | Active option will save to volatile RAM. Server restart is required. |
| [maxBackups](properties/maxBackups.md) | Maximum number of database backups | Once the maximum number of backups is reached, oldest backups will be deleted. |
| [mode](properties/mode.md) | Mode | A stricter synchronization mode lowers the chance that the database is corrupted in case of a crash or power failure. The memory journaling mode can also corrupt the database. |
| [vacuumOnStartup](properties/vacuumOnStartup.md) | Vacuum at start | Tries to reduce database size. This might take a while on big databases. |

## Type definitions

| Name | Description |
| ---- | ----------- |
| [stringTypeArray](definitions/stringTypeArray.md) | Width of the XAxis in milliseconds. |

