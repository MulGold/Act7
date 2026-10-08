# C4 System Context Diagram — [Insert Your MVP System Name]

**Scope:** High-level system context showing external user roles, system boundary, and third-party integrations [1].

```mermaid
C4Context
    title C4 System Context Diagram for [Your MVP System Name]

    %% User Roles / Persons
    Person(primaryUser, "[Primary User Role]", "A [role description, e.g., Customer who requests services].")
    Person(adminUser, "System Administrator", "Manages platform content, user accounts, and system configuration.")

    %% Central MVP System (One Box)
    System(mvpSystem, "[Your MVP System Name]", "[Write a clear one-sentence description of what your software system does].")

    %% External Systems
    System_Ext(paymentSystem, "Payment Gateway", "Processes financial transactions and payment verification.")
    System_Ext(authProvider, "Authentication Service", "Handles OAuth identity verification (e.g., Google/Facebook Login).")
    System_Ext(messagingService, "Notification Service", "Delivers transactional emails and SMS alerts to users.")

    %% Labeled Relationships (Intent / Action)
    Rel(primaryUser, mvpSystem, "Searches for services, submits requests, and views order status")
    Rel(adminUser, mvpSystem, "Monitors activity, audits logs, and updates platform settings")
    Rel(mvpSystem, paymentSystem, "Sends payment requests and receives transaction confirmation")
    Rel(mvpSystem, authProvider, "Delegates user credential validation and token exchange")
    Rel(mvpSystem, messagingService, "Triggers automated notification messages")

    UpdateLayoutConfig(\\(c4ShapeInRow="3", \\)c4BoundaryInRow="1")
```

### Diagram Key
* **Person (Blue Box):** Human user roles that interact directly with the MVP system [1].
* **System (Dark Blue Central Box):** Your MVP software boundary as a single entity [1, 2].
* **System_Ext (Grey Box):** Third-party systems or external services integrated with your MVP [1, 2].
* **Arrows:** Directed interaction paths, labeled with the specific intent or goal of the interaction [1, 2].
