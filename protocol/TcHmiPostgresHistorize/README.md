## General symbols

| Name | Text |
| ---- | ---- |
| [DeleteDatabaseEntries](symbols/DeleteDatabaseEntries.md) | Delete records from the historized database. |
| [Diagnostics](symbols/Diagnostics.md) | Retrieves information about the historized data that is stored in the database. |
| [GetTrendLineData](symbols/GetTrendLineData.md) | Retrieves an array of timestamps and data points for the requested symbol(s). |
| [GetTrendLineWindow](symbols/GetTrendLineWindow.md) | Retrieves the time window for a specific TrendLineChart. |

## General properties

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [compressAfter](properties/compressAfter.md) | Compress after | The interval of TimescaleDB's add_compression_policy determines the point in time from which data is compressed. |
| [compressionScheduleInterval](properties/compressionScheduleInterval.md) | Compression frequency | Scheduled intervals for data compression  |
| [enableCompression](properties/enableCompression.md) | Compression enabled | Compression on large tables can take a significant amount of time. Compression affects storage efficiency and query performance. |
| [historizedSymbolList](properties/historizedSymbolList.md) | Historized symbols | List containing all historized symbols. |

## Database settings

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [databaseSettings](properties/databaseSettings.md) | Current database connection | PostgreSQL database settings |

## Type definitions

| Name | Description |
| ---- | ----------- |
| [pointInTime](definitions/pointInTime.md) | Configure timespan. |

