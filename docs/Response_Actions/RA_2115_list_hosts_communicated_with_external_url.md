| Title                       | List hosts communicated with external URL         |
|:---------------------------:|:--------------------|
| **ID**                      | RA2115            |
| **Description**             | List hosts communicated with an external URL   |
| **Author**                  | @atc_project        |
| **Creation Date**           | 2020/05/06 |
| **Category**                | Network      |
| **Stage**                   |[RS0002: Identification](../Response_Stages/RS0002.md)| 
| **Requirements** |<ul><li>DN_zeek_http_log</li><li>DN_proxy_log</li></ul>|

### Workflow

List hosts communicated with an external URL using the most efficient way.  

## Using Microsoft Defender for Endpoint Advanced Hunting: 

```kusto
// Query the network communication logs to find internal hosts that communicated with the external URL
DeviceNetworkEvents
| where RemoteUrl contains "https://example.com"
| summarize count() by DeviceName, InitiatingProcessAccountUpn, RemoteUrl, InitiatingProcessFileName
```

## Using Crowdstrike Advanced Event Search

Note: Crowdstrike does not log URLs, but you can search for the domain part of the URL.

```kusto
#event_simpleName="DnsRequest"
| DomainName = "example.com"
| groupBy([ComputerName, UserName, ContextBaseFileName, DomainName])
| sort([_count], order=desc)
```