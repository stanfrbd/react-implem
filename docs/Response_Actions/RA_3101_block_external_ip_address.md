| Title                       | Block external IP address         |
|:---------------------------:|:--------------------|
| **ID**                      | RA3101            |
| **Description**             | Block an external IP address from being accessed by corporate assets   |
| **Author**                  | @atc_project        |
| **Creation Date**           | 2019/01/31 |
| **Category**                | Network      |
| **Stage**                   |[RS0003: Containment](../Response_Stages/RS0003.md)| 
| **Requirements** |<ul><li>MS_border_firewall</li><li>MS_border_proxy</li><li>MS_border_ips</li><li>MS_border_ngfw</li><li>MS_host_firewall</li></ul>|

### Workflow

Block an external IP address from being accessed by corporate assets, using the most efficient way.  

Warning:  

- Be careful blocking IP addresses. Make sure it's not a cloud provider or a hoster. If you would like to block something that is hosted on a well-known cloud provider or on a big hoster IP address, you should block (if applicable) a specific URL using alternative Response Action   

## General guidelines

- Make sure you have approval from the CIRT manager before blocking an IP address.
- Use your internal processes and tools to block the IP address.
- Make sure to have traceability of the action (ticket, who did it, logs, etc.).
- Document the action taken in the incident ticket.

Note: don't block IP addresses from well-known cloud providers or hosters, unless you are blocking a specific URL using alternative Response Action.
The IP address don't need to be blocked more than 30 days. After that, you should review if the IP address is still malicious or not (IOC life cycle management).