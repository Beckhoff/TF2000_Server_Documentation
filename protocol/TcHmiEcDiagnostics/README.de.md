## Allgemeine Symbole

| Name | Text |
| ---- | ---- |
| [ClearCrc](symbols/ClearCrc.de.md) | Clear the CRC error statistics of the EtherCAT master. |
| [ClearFrames](symbols/ClearFrames.de.md) | Clear the frame statistics of the EtherCAT master. |
| [Diagnostics](symbols/Diagnostics.de.md) | Get information about the connections between the HMI server and the configured EtherCAT masters. |
| [DisableSlave](symbols/DisableSlave.de.md) | Disable a specific slave of a specific EtherCAT master. |
| [EnableSlave](symbols/EnableSlave.de.md) | Enable a specific slave of a specific EtherCAT master. |
| [ForceProcessDataValues](symbols/ForceProcessDataValues.de.md) | Force a specific value in the process data of a specific EtherCAT master. |
| [GetMaster](symbols/GetMaster.de.md) | Get information about a specific EtherCAT master. |
| [GetMasterOnlineInfo](symbols/GetMasterOnlineInfo.de.md) | Get the online information of a specific EtherCAT master. |
| [GetProcessDataValues](symbols/GetProcessDataValues.de.md) | Get the process data of a specific slave of a specific EtherCAT master. |
| [GetSlaves](symbols/GetSlaves.de.md) | Get information about the slaves of a specific EtherCAT master. |
| [GetSlavesOnlineInfo](symbols/GetSlavesOnlineInfo.de.md) | Get online information from the slaves of a specific EtherCAT master. |
| [GetSlavesScanned](symbols/GetSlavesScanned.de.md) | Get a list of scanned slaves in the network of an EtherCAT master. |
| [GetTarget](symbols/GetTarget.de.md) | Get information about a specific EtherCAT target. |
| [ListConfiguredDevices](symbols/ListConfiguredDevices.de.md) | Get a list of all configured EtherCAT devices. |
| [ListMastersOfRoute](symbols/ListMastersOfRoute.de.md) | Get a list of the EtherCAT masters that are available via a specific ADS route. |
| [ListSlavesWithForcedProcessData](symbols/ListSlavesWithForcedProcessData.de.md) | List of physical addresses of all slaves with forced process data. |
| [ReleaseProcessDataValues](symbols/ReleaseProcessDataValues.de.md) | Release a specific value in the process data of a specific EtherCAT master. |
| [SendSlavesScanCmd](symbols/SendSlavesScanCmd.de.md) | Scan the network for slaves of an EtherCAT master. |
| [SetMasterStateMachine](symbols/SetMasterStateMachine.de.md) | Set the state machine of a specific EtherCAT master. |
| [SetProcessDataValues](symbols/SetProcessDataValues.de.md) | Set a specific value in the process data of a specific EtherCAT master. |
| [SetSlaveStateMachine](symbols/SetSlaveStateMachine.de.md) | Set the state machine of the slave of a specific EtherCAT master. |

## Allgemeine Eigenschaften

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [devices](properties/devices.de.md) | EtherCAT-Geräte | EtherCAT-Geräte |
| [runtimeStateCheckTimeout](properties/runtimeStateCheckTimeout.de.md) | Maximales Timeout bei der Laufzeitstatus-Ermittlung | Eine konfigurierte Laufzeit wird als nicht erreichbar angesehen, wenn eine Anfrage länger als diese Zeitspanne dauert. |
| [updateIntervals](properties/updateIntervals.de.md) | Aktualisierungsintervalle | Minimum time between two asynchronous requests for each request. |
| [vendorsOverwrite](properties/vendorsOverwrite.de.md) | Hersteller-Überschreibung | Hersteller-ID hinzufügen |

## Typ-Definitionen

| Name | Beschreibung |
| ---- | ------------ |
| [EcDiagnosticsProcessDataInOutValues](definitions/EcDiagnosticsProcessDataInOutValues.de.md) | Prozessdaten (IN-OUT-Werte) |
| [EcDiagnosticsProcessDataObjectEntryID](definitions/EcDiagnosticsProcessDataObjectEntryID.de.md) | Prozessdaten (ID) |
| [EcDiagnosticsProcessDataObjectEntryValue](definitions/EcDiagnosticsProcessDataObjectEntryValue.de.md) | Prozessdaten (Wert) |
| [slave](definitions/slave.de.md) | EtherCAT-Slave |

