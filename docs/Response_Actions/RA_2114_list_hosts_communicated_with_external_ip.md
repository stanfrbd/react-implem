| Title                       | List hosts communicated with external IP         |
|:---------------------------:|:--------------------|
| **ID**                      | RA2114            |
| **Description**             | List hosts communicated with an external IP address   |
| **Author**                  | @atc_project        |
| **Creation Date**           | 2020/05/06 |
| **Category**                | Network      |
| **Stage**                   |[RS0002: Identification](../Response_Stages/RS0002.md)| 
| **Requirements** |<ul><li>DN_network_flow_log</li><li>DN_zeek_conn_log</li></ul>|

### Workflow

List hosts communicated with an external IP address using the most efficient way.  

## Using Microsoft Defender for Endpoint Advanced Hunting: 

```kusto
DeviceNetworkEvents
| where RemoteIP == "1.1.1.1"
| summarize count() by DeviceName, InitiatingProcessAccountUpn, RemoteIP, InitiatingProcessFileName
```

## Using Crowdstrike Advanced Event Search

```kusto
#event_simpleName="NetworkConnectIP4"
| RemoteIP = "1.1.1.1"
| groupBy([ComputerName, UserName, ContextBaseFileName, RemoteIP])
| sort([_count], order=desc)
```