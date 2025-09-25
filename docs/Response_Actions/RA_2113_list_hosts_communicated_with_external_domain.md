| Title                       | List hosts communicated with external domain         |
|:---------------------------:|:--------------------|
| **ID**                      | RA2113            |
| **Description**             | List hosts communicated with an external domain   |
| **Author**                  | @atc_project        |
| **Creation Date**           | 2020/05/06 |
| **Category**                | Network      |
| **Stage**                   |[RS0002: Identification](../Response_Stages/RS0002.md)| 
| **Requirements** |<ul><li>DN_zeek_conn_log</li><li>DN_zeek_dns_log</li><li>DN_zeek_http_log</li><li>DN_dns_log</li><li>DN_proxy_log</li><li>DN_network_flow_log</li></ul>|

### Workflow

List hosts communicated with an external domain using the most efficient way.  

## Using Microsoft Defender for Endpoint Advanced Hunting: 

Note: MDE does not log domains directly, but you can search for URLs containing the domain.

```kusto
DeviceNetworkEvents
| where RemoteUrl contains "example.com"
| summarize count() by DeviceName, InitiatingProcessAccountUpn, RemoteUrl, InitiatingProcessFileName
```

## Using Crowdstrike Advanced Event Search

```kusto
#event_simpleName="DnsRequest"
| DomainName = "example.com"
| groupBy([ComputerName, UserName, ContextBaseFileName, DomainName])
| sort([_count], order=desc)
```