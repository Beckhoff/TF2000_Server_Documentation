## Allgemeine Symbole

| Name | Text |
| ---- | ---- |
| [Diagnostics](symbols/Diagnostics.de.md) | Get information about the connections between the HMI server and the ADS targets. |
| [GetSchema](symbols/GetSchema.de.md) | Get the schema of a specific dynamic symbol. |
| [ListCommonTypes](symbols/ListCommonTypes.de.md) | Get a list of common ADS datatypes. |
| [ListSymbols](symbols/ListSymbols.de.md) | List all dynamic symbols. |

## Native ADS-Funktionen

| Name | Text |
| ---- | ---- |
| [AdsSyncReadDeviceInfoReq](symbols/AdsSyncReadDeviceInfoReq.de.md) | Reads the identification and version number of an ADS server. |
| [AdsSyncReadReq](symbols/AdsSyncReadReq.de.md) | Reads data synchronously from an ADS server. |
| [AdsSyncReadStateReq](symbols/AdsSyncReadStateReq.de.md) | Reads the ADS status and the device status of an ADS server. |
| [AdsSyncReadWriteReq](symbols/AdsSyncReadWriteReq.de.md) | Writes data synchronously into an ADS server and receives data back from the ADS device. |
| [AdsSyncWriteControlReq](symbols/AdsSyncWriteControlReq.de.md) | Changes the ADS status and the device status of an ADS server. |
| [AdsSyncWriteReq](symbols/AdsSyncWriteReq.de.md) | Writes data synchronously to an ADS device. |

## Wrapper-Funktionen

| Name | Text |
| ---- | ---- |
| [CheckLicense](symbols/CheckLicense.de.md) | Get information about a specific license by sending a request to the TwinCAT license server. |
| [GetSystemId](symbols/GetSystemId.de.md) | Get a the local TwinCAT System ID. |
| [ListRoutes](symbols/ListRoutes.de.md) | Get a list of the TwinCAT ADS routes. |
| [RuntimePorts](symbols/RuntimePorts.de.md) | List the runtime ports of a specific TwinCAT system. |

## Allgemeine Eigenschaften

| Symbolname | Text | Beschreibung |
| ---------- | ---- | ------------ |
| [ENABLE_READ_BEFORE_WRITE](properties/ENABLE_READ_BEFORE_WRITE.de.md) | Unvollständige Schreiboperationen durch Lesen vor dem Schreiben unterstützen | Variablen, die versteckt oder in der Schreibanforderung nicht gesetzt sind, werden mit einem alten Wert überschrieben. Deaktivieren Sie diese Einstellung, um Seiteneffekte zu vermeiden und die Leistung zu verbessern. |
| [IGNORED_PLC_ATTRIBUTES](properties/IGNORED_PLC_ATTRIBUTES.de.md) | Ignorierte PLC-Attribute | Attribut-Pragmas werden zum JSON-Schema hinzugefügt. Die hier konfigurierten Attribute werden ausgeblendet. |
| [NEW_HANDLES_PER_SUM_REQUEST_LIMIT](properties/NEW_HANDLES_PER_SUM_REQUEST_LIMIT.de.md) | Begrenzung der Anzahl von ADS-Handles, die mit einer Summen-Anfrage erstellt werden | TwinCATs Handle-Buffer wird nicht während einer Summen-Anfrage vergrößert. Das Anlegen von zu vielen ADS-Handles in einer einzigen Summen-Anfrage führt zu Fehlern, wenn TwinCATs Handle-Buffer voll ist. |
| [RESPONSE_SIZE_LIMIT](properties/RESPONSE_SIZE_LIMIT.de.md) | Begrenzung der Antwortgröße von ADS-Anfragen | Die SPS-Task wird für jede Anfrage gesperrt. Ist die Anfrage zu groß, kann die SPS-Zykluszeit überschritten werden. |
| [RUNTIMES](properties/RUNTIMES.de.md) | Laufzeiten | Zu allen aktiven Laufzeiten wird eine ADS-Verbindung hergestellt. |
| [RUNTIME_STATE_CHECK_INTERVAL](properties/RUNTIME_STATE_CHECK_INTERVAL.de.md) | Intervall der Laufzeitstatus-Ermittlung | Der Status jeder konfigurierten Laufzeit wird in regelmäßigen Abständen überprüft. |
| [RUNTIME_STATE_CHECK_TIMEOUT](properties/RUNTIME_STATE_CHECK_TIMEOUT.de.md) | Maximales Timeout bei der Laufzeitstatus-Ermittlung | Eine konfigurierte Laufzeit wird als nicht erreichbar angesehen, wenn eine Anfrage länger als diese Zeitspanne dauert. |
| [SUM_REQUEST_LIMIT](properties/SUM_REQUEST_LIMIT.de.md) | Begrenzung der Anzahl von ADS-Anfragen, die in einer Summen-Anfrage gebündelt werden können | Die PLC-Task ist für jede Anfrage gesperrt. Wenn eine Summen-Anfrage zu viele Anfragen enthält, kann die SPS-Zykluszeit überschritten werden. |
| [TIMEOUT](properties/TIMEOUT.de.md) | Timeout | Standard-Timeout für ADS-Anfragen. |
| [VISIBLE_RUNTIME_PORTS](properties/VISIBLE_RUNTIME_PORTS.de.md) | Sichtbare Laufzeitports | Zielsysteme können viele ADS-Ports haben. Die meisten werden nur selten in HMI-Projekten verwendet. |

## Typ-Definitionen

| Name | Beschreibung |
| ---- | ------------ |
| [adsState](definitions/adsState.de.md) |  |

