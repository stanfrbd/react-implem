| Title                       | Takedown external domain         |
|:---------------------------:|:--------------------|
| **ID**                      | RA3103-C            |
| **Description**             | Custom - Takedown external domain by contacting the registrar or hosting provider   |
| **Author**                  | @stanfrbd        |
| **Creation Date**           | 2025/09/26 |
| **Category**                | Network      |
| **Stage**                   |[RS0003: Containment](../Response_Stages/RS0003.md)| 
| **References** |<ul><li></li></ul>|
| **Requirements** | |

### Workflow

1. **Identify the Domain Registrar and Hosting Provider**  
    - Use WHOIS lookup tools (e.g., [whois.domaintools.com](https://whois.domaintools.com/), [ICANN WHOIS](https://whois.icann.org/en)) to find the registrar and hosting provider information for the domain.  
    - Note down the contact details, abuse email addresses, and any relevant policies regarding abuse reports.
    - You can use [Cyberbro](https://github.com/stanfrbd/cyberbro) for this.

2. **Gather Evidence of Malicious Activity**  
    - Compile all relevant information that demonstrates the domain's malicious activity, such as:  
      - Logs showing traffic to/from the domain.  
      - Screenshots of phishing pages or malware hosted on the domain.  
      - Reports from threat intelligence platforms (e.g., VirusTotal, AlienVault OTX).  
      - Any other relevant indicators of compromise (IOCs).

3. **Draft a Takedown Request**
    - Write a clear and concise takedown request email to the registrar and hosting provider. Include:  
      - A description of the malicious activity associated with the domain.  
      - The evidence you have gathered.  
      - A request for immediate action to take down the domain or block access to it.  
      - Your contact information for follow-up.
    - Use a professional tone and be specific about the actions you want them to take.

4. **Send the Takedown Request**
    - Send the takedown request to the abuse contact email addresses identified in step 1.  
    - If no response is received within a reasonable timeframe (e.g., 48-72 hours), consider sending a follow-up email.

Note: sometimes the provider will send a form to fill in instead of answering directly to the email.