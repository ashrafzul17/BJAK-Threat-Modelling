# Data Flow Diagram

Below is a high-level Data Flow Diagram for the BJAK insurance comparison platform, outlining the flow of data between users, the platform, and third-party service providers.

```mermaid
graph TD
    subgraph User Interaction
        A[User] -->|Access Website| B[BJAK Frontend]
    end

    subgraph BJAK Backend
        B -->|Submit Input| C[Backend Server]
        C -->|Validate Data| D[Input Validation Service]
        C -->|Process Request| E[Insurance Quote Service]
    end

    subgraph Third-Party Integration
        E -->|API Call| F[Insurance Providers API]
    end

    F -->|Return Response| G[Quote Results]
    G -->|Display Data| B

    %% Additional Security Controls
    B -.->|Authentication| H[Authentication Mechanism]
    C -.->|Logging| I[Logging Service]
