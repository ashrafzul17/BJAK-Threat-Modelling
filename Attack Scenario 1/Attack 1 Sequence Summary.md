# Summary MITRE ATT&CK Sequence

## Attack Description

The attacker in this scenario conducts a credential stuffing attack using lists of leaked or stolen user credentials. By utilizing automated tools, the attacker attempts multiple logins for every possible username, exploiting weak password policies or reused credentials across multiple platforms. Once valid account credentials are found, the attacker gains unauthorized access to user accounts, potentially leveraging this to access sensitive data or escalate privileges.

## Methodology

The attack sequence below utilises the MITRE ATT&CK framework along with commonly used techniques.

```mermaid
flowchart TD

    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Obtain user credentials from leaks or dark web| Weaponization[Weaponization]

    Weaponization[Weaponization] -->|Utilize automated login tools for credential stuffing| Delivery[Delivery]

    Delivery[Delivery] -->|Automated login attempts with large set of user credentials| Exploitation[Exploitation]

    Exploitation[Exploitation] -->|Successful login due to weak passwords or reused credentials| Installation[Installation]

    Installation[Installation] -->|Gain unauthorized access to backend or user profiles| Command_Control[Command and Control]

    Command_Control[Command and Control] -->|Use compromised accounts to execute additional commands| Actions_Objectives[Actions on Objectives]

    Actions_Objectives[Actions on Objectives] -->|Access sensitive data or escalate privileges| Actions_Objectives[Actions on Objectives]

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    Delivery -->|T1071.001 - Application Layer Protocol: Web Protocols| MITRE
    Exploitation -->|T1071.001 - Exploit Public-Facing Application| MITRE
    Exploitation -->|T1071.003 - Credential Dumping| MITRE
    Command_Control -->|T1071.001 - Web Service| MITRE
    Command_Control -->|T1071.003 - Command and Scripting Interpreter| MITRE
    Actions_Objectives -->|T1071.005 - Data Manipulation| MITRE
    Actions_Objectives -->|T1071.006 - Data Exfiltration| MITRE
    end
