# High-Level Design

This document outlines the architecture and components of the BJAK platform.

## Architecture Components

- **Frontend**: A responsive web application that provides a user-friendly interface for customers to input insurance comparison requests.
  - Framework: React.js
  - Security: Implements Content Security Policy (CSP) and HTTPS.

- **Backend**: A robust API service that handles all business logic and integration with third-party insurance providers.
  - Framework: Node.js with Express.
  - Security: Input validation, rate limiting, and anti-bot mechanisms.

- **Third-Party Integration**: APIs to interact with insurance providers for fetching and comparing quotes.
  - Communication: RESTful APIs with OAuth2 for authentication.
  - Security: SSL encryption and payload integrity validation.


   ## System Design Diagram

The following diagram provides an overview of the BJAK system architecture:

```mermaid
flowchart TD

    subgraph "User Interface"
        UI[User Interface]
    end

    subgraph "Frontend (Web Server)"
        FE[Frontend Server]
    end

    subgraph "Backend Services"
        BE[Backend Server]
    end

    subgraph "Database Layer"
        DB[Database Server]
    end

    subgraph "Third-Party Integration"
        TP[Insurance Providers API]
    end

    subgraph "External Services"
        Logging[Logging Service]
        Auth[Authentication Mechanism]
    end

    UI --> FE
    FE --> BE
    BE --> DB
    BE --> TP
    BE -.-> Logging
    FE -.-> Auth