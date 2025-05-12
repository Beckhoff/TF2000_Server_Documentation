## General symbols

| Name | Text |
| ---- | ---- |
| [Diagnostics](symbols/Diagnostics.md) | Get information about the connections between the HMI server and the ADS targets. |
| [GetSchema](symbols/GetSchema.md) | Get the schema of a specific dynamic symbol. |
| [ListCommonTypes](symbols/ListCommonTypes.md) | Get a list of common ADS datatypes. |
| [ListSymbols](symbols/ListSymbols.md) | List all dynamic symbols. |

## Native ADS functions

| Name | Text |
| ---- | ---- |
| [AdsSyncReadDeviceInfoReq](symbols/AdsSyncReadDeviceInfoReq.md) | Reads the identification and version number of an ADS server. |
| [AdsSyncReadReq](symbols/AdsSyncReadReq.md) | Reads data synchronously from an ADS server. |
| [AdsSyncReadStateReq](symbols/AdsSyncReadStateReq.md) | Reads the ADS status and the device status of an ADS server. |
| [AdsSyncReadWriteReq](symbols/AdsSyncReadWriteReq.md) | Writes data synchronously into an ADS server and receives data back from the ADS device. |
| [AdsSyncWriteControlReq](symbols/AdsSyncWriteControlReq.md) | Changes the ADS status and the device status of an ADS server. |
| [AdsSyncWriteReq](symbols/AdsSyncWriteReq.md) | Writes data synchronously to an ADS device. |

## Wrapper functions

| Name | Text |
| ---- | ---- |
| [CheckLicense](symbols/CheckLicense.md) | Get information about a specific license by sending a request to the TwinCAT license server. |
| [GetSystemId](symbols/GetSystemId.md) | Get a the local TwinCAT System ID. |
| [ListRoutes](symbols/ListRoutes.md) | Get a list of the TwinCAT ADS routes. |
| [RuntimePorts](symbols/RuntimePorts.md) | List the runtime ports of a specific TwinCAT system. |

## General properties

| Symbol name | Text | Description |
| ----------- | ---- | ----------- |
| [ENABLE_READ_BEFORE_WRITE](properties/ENABLE_READ_BEFORE_WRITE.md) | Support incomplete writes by reading before writing | Variables that are hidden or not set in the write request will be overwritten with an old value. Disable this setting to prevent side effects and improve performance. |
| [IGNORED_PLC_ATTRIBUTES](properties/IGNORED_PLC_ATTRIBUTES.md) | Ignored PLC attributes | Attribute pragmas are added to the JSON schema. The attributes configured here are hidden. |
| [NEW_HANDLES_PER_SUM_REQUEST_LIMIT](properties/NEW_HANDLES_PER_SUM_REQUEST_LIMIT.md) | Limit the number of ADS handles created by a sum request | TwinCAT's handle buffer is not resized in the middle of a sum request. Creating too many ADS handles in a single sum request causes errors if TwinCAT's handle buffer is full. |
| [RESPONSE_SIZE_LIMIT](properties/RESPONSE_SIZE_LIMIT.md) | Limit response size of ADS requests | The PLC task is locked for every request. If the request is too large, the PLC cycle time might be exceeded. |
| [RUNTIMES](properties/RUNTIMES.md) | Runtimes | An ADS connection is established to all enabled runtimes. |
| [RUNTIME_STATE_CHECK_INTERVAL](properties/RUNTIME_STATE_CHECK_INTERVAL.md) | Runtime state check interval | The state of each configured runtime is checked periodically. |
| [RUNTIME_STATE_CHECK_TIMEOUT](properties/RUNTIME_STATE_CHECK_TIMEOUT.md) | Maximum timeout for determining the runtime status | A configured runtime is considered unreachable if a request takes longer than this timeout. |
| [SUM_REQUEST_LIMIT](properties/SUM_REQUEST_LIMIT.md) | Limit the number of ADS requests that can be bundled in one sum request | The PLC task is locked for every request. If a sum request contains too many requests, the PLC cycle time might be exceeded. |
| [TIMEOUT](properties/TIMEOUT.md) | Timeout | Default timeout for ADS requests. |
| [VISIBLE_RUNTIME_PORTS](properties/VISIBLE_RUNTIME_PORTS.md) | Visible runtime ports | Target systems can have many ADS ports. Most are rarely used in HMI projects. |

## Type definitions

| Name | Description |
| ---- | ----------- |
| [adsState](definitions/adsState.md) |  |

