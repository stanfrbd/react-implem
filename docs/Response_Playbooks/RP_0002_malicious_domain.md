| Title             | Malicious Domain                                                                                                      |
|:-----------------:|:-----------------------------------------------------------------------------------------------------------------|
| **ID**            | RP0002            |
| **Description**   | Response playbook for Malicious Domain case   |
| **Author**        | @stanfrbd        |
| **Creation Date** | 2025/09/26 |
| **Severity**      | M      |
| **TLP**           | WHITE           |
| **PAP**           | WHITE           |
| **ATT&amp;CK Tactic**  |<ul><li>[TA0001: Initial Access](https://attack.mitre.org/tactics/TA0001)</li></ul>|
| **ATT&amp;CK Technique**  |<ul></ul>|
| **Tags**          | <ul><li>phishing</li></ul> |


```mermaid
flowchart TD
    ALERT(("Alert received")) --> ANALYZE["RA2104: Analyze domain name"]
    ANALYZE --> DECISION{"Domain Assessment"}
    DECISION -- Legitimate --> UPDATE_ASSETS["Update Global Assets File"]
    UPDATE_ASSETS --> CLOSE_BENIGN["Close as Benign Positive"]
    DECISION -- Not harmful --> ADD_TO_WATCHLIST["Add to Watchlist"]
    ADD_TO_WATCHLIST --> CLOSE_BENIGN
    DECISION -- Malicious --> TAKEDOWN["RA3103-C: Takedown External Domain"]
    TAKEDOWN --> BLOCK_EMAIL["RA3201: Block Domain on Email"]
    BLOCK_EMAIL --> BLOCK_NET["RA3103: Block External Domain"]
    BLOCK_NET --> CLOSE_TRUE_POSITIVE["Close as True Positive"]
    
    style ALERT fill:#AA00FF,color:#000000
    style DECISION fill:#FF6D00,color:#000000
    style CLOSE_BENIGN fill:#9f9,color:#000000
    style CLOSE_TRUE_POSITIVE fill:#f96,color:#000000

    click ANALYZE "../Response_Actions/RA_2104_analyse_domain_name"
    click TAKEDOWN "../Response_Actions/RA_3103_c_takedown_external_domain"
    click BLOCK_EMAIL "../Response_Actions/RA_3201_block_domain_on_email"
    click BLOCK_NET "../Response_Actions/RA_3103_block_external_domain"