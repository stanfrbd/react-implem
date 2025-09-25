| Title                       | Analyse domain name         |
|:---------------------------:|:--------------------|
| **ID**                      | RA2104            |
| **Description**             | Analyse a domain name   |
| **Author**                  | name/nickname/twitter        |
| **Creation Date**           | YYYY/MM/DD |
| **Category**                | Network      |
| **Stage**                   |[RS0002: Identification](../Response_Stages/RS0002.md)| 
| **Automation** |<ul><li>thehive</li></ul>|
| **References** |<ul><li>[https://example.com](https://example.com)</li></ul>|

### Workflow

1. **Initial Context Gathering**  
    - Source of domain: Identify how the domain was flagged (e.g., SIEM alert, phishing email, firewall logs).  
    - Associated activity: Note any suspicious behavior (e.g., data exfiltration, command-and-control traffic).  
    - Timestamp: Record when the domain was first observed.  

2. **Passive DNS and WHOIS Lookup**  
    - WHOIS data:  
      - Registrar, registration date, expiration date.  
      - Contact info (often redacted or privacy-protected).  
      - Check for recently registered domains (often suspicious).  
    - Passive DNS:  
      - Historical IP resolutions.  
      - Subdomains and related domains.  
      - Changes in hosting infrastructure.  
    - Be cautious about DNS records, including MX records and TXT records.

3. **Reputation and Threat Intelligence Checks**  
    - Query the domain against:  
      - VirusTotal  
      - MDTI  
      - Cyberbro  
      - Google with dorks  
    - Look for:  
      - Blacklist status.  
      - Associated malware or phishing campaigns.  
      - Related threat actor infrastructure.

4. **Open Source Intelligence (OSINT)**  
    - Search the domain on:  
      - Google, Reddit, Twitter, forums.  
      - Security blogs or GitHub repositories.  
    - Look for:  
      - Reports of abuse.  
      - Indicators of compromise (IOCs).  
      - Connections to known campaigns.

5. **Infrastructure and Hosting Analysis**  
    - IP geolocation: Where is the domain hosted?  
    - ASN info: Is it part of a suspicious autonomous system?  
    - SSL certificate:  
      - Check issuer, validity, and subject.  
      - Self-signed or Let's Encrypt certificates may raise flags in some contexts.

6. **Behavioral and Content Analysis**  
    - Sandboxing:  
      - Use tools like URLScan.io or Any.Run to analyze domain behavior.  
    - Manual inspection:  
      - Visit the domain in a secure VM or isolated browser.  
      - Look for phishing pages, drive-by downloads, or obfuscated scripts.

7. **Correlation and Enrichment**  
    - Cross-reference with:  
      - Internal logs (proxy, firewall, EDR, ITSM).  
      - Other IOCs (IP addresses, file hashes).  
      - MITRE ATT&CK techniques.

**Identify Outcome**  
    - Determine if the domain is legitimate.  
    - Assess if the domain is malicious.  
    - Confirm if the domain is not harmful.

### External resources

- [GoPivot Domain Artifacts](https://gopivot.ing/artifacts/domain/)