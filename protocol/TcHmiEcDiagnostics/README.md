## General symbols

| Name | Text |
| ---- | ---- |
| [ClearCrc](symbols/ClearCrc.md) | Clear the CRC error statistics of the EtherCAT master. |
| [ClearFrames](symbols/ClearFrames.md) | Clear the frame statistics of the EtherCAT master. |
| [Diagnostics](symbols/Diagnostics.md) | Get information about the connections between the HMI server and the configured EtherCAT masters. |
| [DisableSlave](symbols/DisableSlave.md) | Disable a specific slave of a specific EtherCAT master. |
| [EnableSlave](symbols/EnableSlave.md) | Enable a specific slave of a specific EtherCAT master. |
| [ForceProcessDataValues](symbols/ForceProcessDataValues.md) | Force a specific value in the process data of a specific EtherCAT master. |
| [GetMaster](symbols/GetMaster.md) | Get information about a specific EtherCAT master. |
| [GetMasterOnlineInfo](symbols/GetMasterOnlineInfo.md) | Get the online information of a specific EtherCAT master. |
| [GetProcessDataValues](symbols/GetProcessDataValues.md) | Get the process data of a specific slave of a specific EtherCAT master. |
| [GetSlaves](symbols/GetSlaves.md) | Get information about the slaves of a specific EtherCAT master. |
| [GetSlavesOnlineInfo](symbols/GetSlavesOnlineInfo.md) | Get online information from the slaves of a specific EtherCAT master. |
| [GetSlavesScanned](symbols/GetSlavesScanned.md) | Get a list of scanned slaves in the network of an EtherCAT master. |
| [GetTarget](symbols/GetTarget.md) | Get information about a specific EtherCAT target. |
| [ListConfiguredDevices](symbols/ListConfiguredDevices.md) | Get a list of all configured EtherCAT devices. |
| [ListMastersOfRoute](symbols/ListMastersOfRoute.md) | Get a list of the EtherCAT masters that are available via a specific ADS route. |
| [ListSlavesWithForcedProcessData](symbols/ListSlavesWithForcedProcessData.md) | List of physical addresses of all slaves with forced process data. |
| [ReleaseProcessDataValues](symbols/ReleaseProcessDataValues.md) | Release a specific value in the process data of a specific EtherCAT master. |
| [SendSlavesScanCmd](symbols/SendSlavesScanCmd.md) | Scan the network for slaves of an EtherCAT master. |
| [SetMasterStateMachine](symbols/SetMasterStateMachine.md) | Set the state machine of a specific EtherCAT master. |
| [SetProcessDataValues](symbols/SetProcessDataValues.md) | Set a specific value in the process data of a specific EtherCAT master. |
| [SetSlaveStateMachine](symbols/SetSlaveStateMachine.md) | Set the state machine of the slave of a specific EtherCAT master. |

## General properties

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [devices](properties/devices.md) | EtherCAT devices | EtherCAT devices |
| [runtimeStateCheckTimeout](properties/runtimeStateCheckTimeout.md) | Maximum timeout for determining the runtime status | A configured runtime is considered unreachable if a request takes longer than this timeout. |
| [updateIntervals](properties/updateIntervals.md) | Update intervals | Minimum time between two asynchronous requests for each request. |
| [vendorsOverwrite](properties/vendorsOverwrite.md) | Vendors overwrite | Add vendor ID |

## Type definitions

| Name | Description |
| ---- | ----------- |
| [EcDiagnosticsProcessDataInOutValues](definitions/EcDiagnosticsProcessDataInOutValues.md) | Process data (IN-OUT values) |
| [EcDiagnosticsProcessDataObjectEntryID](definitions/EcDiagnosticsProcessDataObjectEntryID.md) | Process data (object entry ID) |
| [EcDiagnosticsProcessDataObjectEntryValue](definitions/EcDiagnosticsProcessDataObjectEntryValue.md) | Process data (object entry value) |
| [slave](definitions/slave.md) | EtherCAT slave |

