In this example of the STRIDE model, we demonstrate the current controls in place for BJAK's application and use it to reason about and identify potential threats to the system.

```mermaid 
graph TD  

    subgraph User Interaction  
        A[User] -->|HTTP Requests| B[Authentication Server]  
    end  

    subgraph Authentication Server  
        B -->|Validate| C[Credential Validation]  
        B -->|Log Requests| D[Login Monitoring]  
    end  

    subgraph Backend  
        C -->|Fetch User Details| E[Database]  
        C -->|Check Session| F[Session Management]  
    end  

    subgraph External Services  
        G[Third-Party Notification System] -->|Account Alerts| A  
    end  

    A((User)) -.->|Authentication| H[Multi-Factor Authentication (MFA)]  
    B -.->|Logging| I[Security Information and Event Management (SIEM)]  

    %% Threats  
    T1([Spoofing: Spoof User Identity]) -.-> A  
    T2([Tampering: Manipulate Login Data]) -.-> B  
    T3([Repudiation: Deny Credential Use]) -.-> I  
    T4([Information Disclosure: User Data Leak]) -.-> E  
    T5([Denial of Service: Exhaust Server Resources]) -.-> B  
    T6([Elevation of Privilege: Unauthorized Account Access]) -.-> F  

    %% Mitigations  
    M1([Mitigation: Strong Password Policies]) --> T1  
    M2([Mitigation: Secure Communication Channels (HTTPS)]) --> T2  
    M3([Mitigation: Comprehensive Logging and Non-Repudiation]) --> T3  
    M4([Mitigation: Data Encryption at Rest and in Transit]) --> T4  
    M5([Mitigation: Rate Limiting and CAPTCHA]) --> T5  
    M6([Mitigation: Role-Based Access Control and MFA]) --> T6  


