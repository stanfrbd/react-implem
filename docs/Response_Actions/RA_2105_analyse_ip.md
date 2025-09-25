| Title                       | Analyse IP         |
|:---------------------------:|:--------------------|
| **ID**                      | RA2105            |
| **Description**             | Analyse an IP address   |
| **Author**                  | name/nickname/twitter        |
| **Creation Date**           | YYYY/MM/DD |
| **Category**                | Network      |
| **Stage**                   |[RS0002: Identification](../Response_Stages/RS0002.md)| 
| **Automation** |<ul><li>thehive</li></ul>|
| **References** |<ul><li>[https://example.com](https://example.com)</li></ul>|

### Workflow

1. **Initial Context Gathering**  
    - Source of IP: Identify how the IP was flagged (e.g., SIEM alert, IDS/IPS logs, firewall logs).  
    - Associated activity: Note any suspicious behavior (e.g., brute force attempts, data exfiltration).  
    - Timestamp: Record when the IP was first observed.  
    - Use Microsoft Defender Threat Intelligence (MDTI) for IP analysis and CTI correlation.

2. **WHOIS and Geolocation Lookup**  
    - WHOIS data:  
      - ISP, organization, and contact information.  
      - Registration and allocation details.  
    - Geolocation:  
      - Country, region, and city.  
      - Check for unusual or suspicious hosting locations.  

3. **Reputation and Threat Intelligence Checks**  
    Query the IP against:  
    - [VirusTotal](https://www.virustotal.com)   
    - [Cyberbro](https://github.com/stanfrbd/cyberbro)  
    - [AbuseIPDB](https://www.abuseipdb.com)  
    - [IPinfo](https://ipinfo.io)  
    - [AlienVault OTX](https://otx.alienvault.com)
    - [Microsoft Defender Threat Intelligence (MDTI)](https://security.microsoft.com/threatintelligence)   
    - Look for:  
      - Blacklist status.  
      - Associated malware or botnet activity.  
      - Connections to known threat actor infrastructure.

4. **Open Source Intelligence (OSINT)**  
    - Search the IP on:  
      - Google, forums, and social media.  
      - Security blogs or GitHub repositories.  
    - Look for:  
      - Reports of abuse.  
      - Indicators of compromise (IOCs).  
      - Connections to known campaigns.

5. **Network and Traffic Analysis**  
    - Check internal logs:  
      - Firewall, proxy, and EDR logs for traffic to/from the IP.  
      - Look for unusual patterns or volumes of traffic.  
    - Analyze connections:  
      - Identify associated domains, subdomains, or other IPs.  
      - Check for lateral movement or data exfiltration.

6. **Behavioral and Content Analysis**  
    - Sandboxing:  
      - Use tools like Cuckoo Sandbox or Any.Run to analyze traffic behavior.  
    - Manual inspection:  
      - Investigate services running on the IP (e.g., HTTP, FTP, SSH).  
      - Look for suspicious banners, open ports, or misconfigurations.

7. **Correlation and Enrichment**  
    - Cross-reference with:  
      - Internal logs (proxy, firewall, EDR, ITSM).  
      - Other IOCs (domains, file hashes).  
      - MITRE ATT&CK techniques.

**Identify Outcome**  
    - Determine if the IP is legitimate.  
    - Assess if the IP is malicious.  
    - Confirm if the IP is not harmful.

### External resources

- [GoPivot IP Address Artifacts](https://gopivot.ing/artifacts/ip-address/)