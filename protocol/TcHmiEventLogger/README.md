## General symbols

| Name | Text |
| ---- | ---- |
| [ClearLoggedEvents](symbols/ClearLoggedEvents.md) | Clear the event database of a specific target system. |
| [Diagnostics](symbols/Diagnostics.md) | Get information about the connections between the HMI serer and the configured target systems. |
| [ListEnabledTargetSystems](symbols/ListEnabledTargetSystems.md) | Get a list of all enabled target systems. |

## General properties

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [LIMIT_EVENT_COUNT](properties/LIMIT_EVENT_COUNT.md) | Limit event count | Active alarms are always imported, even if this limit is exceeded as a result. |
| [PRELOAD_TRANSLATIONS](properties/PRELOAD_TRANSLATIONS.md) | Preload translations | Improve latency of the event import by reducing the number of network roundtrips for localization. |
| [TARGET_SYSTEMS](properties/TARGET_SYSTEMS.md) | Target systems | Target systems from which events and alarms are collected. |
| [TIMEOUT](properties/TIMEOUT.md) | Timeout | Default timeout for TwinCAT EventLogger requests. |

