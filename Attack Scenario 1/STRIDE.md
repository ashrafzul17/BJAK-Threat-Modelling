# STRIDE Model

In this example of the STRIDE model, we demonstrate the current controls in place for the application and use it to reason about and identify potential threats to the system.

```mermaid
graph TD  

    subgraph User_Interaction  
        A[User] -->|HTTP Requests| B[Authentication_Server]  
    end  

    subgraph Authentication_Server  
        B -->|Validate| C[Credential_Validation]  
        B -->|Log Requests| D[Login_Monitoring]  
    end  

    subgraph Backend  
        C -->|Fetch User Details| E[Database]  
        C -->|Check Session| F[Session_Management]  
    end  

    A((User)) -.->|Authentication| H[Multi-Factor_Authentication]  
    B -.->|Logging| I[SIEM]  

    %% Threats  
    T1([Spoofing: Spoof User Identity]) -.-> A  
    T2([Tampering: Manipulate Login Data]) -.-> B  
    T3([Repudiation: Deny Credential Use]) -.-> I  
    T4([Information Disclosure: User Data Leak]) -.-> E  
    T5([Denial of Service: Exhaust Server Resources]) -.-> B  
    T6([Elevation of Privilege: Unauthorized Access]) -.-> F  

    %% Mitigations  
    M1([Mitigation: Strong Password Policies]) --> T1  
    M2([Mitigation: Secure HTTPS Communication]) --> T2  
    M3([Mitigation: Logging and Non-repudiation]) --> T3  
    M4([Mitigation: Data Encryption]) --> T4  
    M5([Mitigation: Rate Limiting]) --> T5  
    M6([Mitigation: Role-Based Access Control and MFA]) --> T6  
