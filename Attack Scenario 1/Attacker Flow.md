# Attacker Flow: Scenario 1

This flow diagram represents the sequence in which the attacker is leveraging credential stuffing techniques to gain unauthorized access, use those credentials for malicious activities, and potentially escalate their access in the system.

```mermaid
sequenceDiagram
    participant Attacker
    participant WebApp
    participant Database
    participant User

    activate Attacker
    Attacker->>WebApp: Identify login page and target accounts
    WebApp->>Attacker: Login page found
    deactivate Attacker

    activate Attacker
    Attacker->>WebApp: Automated credential stuffing attack (usernames + leaked passwords)
    WebApp->>Attacker: Account authentication failure
    deactivate Attacker

    activate Attacker
    Attacker->>WebApp: Identify accounts with successful login attempts
    WebApp->>Attacker: Accounts logged in successfully
    deactivate Attacker

    activate Attacker
    Attacker->>WebApp: Perform actions on compromised accounts (view sensitive data, make changes)
    WebApp->>Database: Request data for user account
    Database->>WebApp: Data returned (sensitive personal data)
    WebApp->>Attacker: Data exfiltrated
    deactivate Attacker

    activate Attacker
    Attacker->>WebApp: Elevate privileges or escalate access for additional damage
    WebApp->>Attacker: New access granted (admin or super user role)
    deactivate Attacker

    activate Attacker
    Attacker->>User: Account credentials sent to the attacker
    User->>Attacker: Malicious activity continues (data manipulation, unauthorized access)
    deactivate Attacker
