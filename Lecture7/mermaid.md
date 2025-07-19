# 1. Lecture Notes

# Lecture: Using Diverse Mermaid Diagrams for Software Design & Development

---

## 1. Introduction to Mermaid

- Mermaid is a text-based diagramming tool supporting multiple diagram types:
  - Flowcharts, Mindmaps, Class diagrams, Sequence diagrams
  - Requirement diagrams, Kanban boards, Gantt charts
- Using the right diagram type clarifies communication in software projects.

---

## 2. Project Kick-off: Mindmap Diagram

```mermaid
mindmap
  root((Project Kickoff))
    Stakeholders
      Developers
      QA
      Product Owner
    Goals
      Scope Definition
      Timeline Planning
      Risks
    Resources
      Budget
      Tools
      Team
````

*Mindmaps help brainstorm scope, stakeholders, and goals.*

---

## 3. Requirements Gathering: Requirement Diagram (7 min)

```mermaid
requirementDiagram
  requirement req1 {
    id: R1
    text: "User login must be secure"
    risk: high
    verifymethod: test
  }
  requirement req2 {
    id: R2
    text: "System must handle 10,000 concurrent users"
    risk: medium
    verifymethod: test
  }
element test_req1 {
    type: Manual Test
    }
element test_req2 {
    type: Performance Test
    }

  test_req1 - satisfies -> req1
  test_req2 - satisfies -> req2
```

*Shows requirements, risks, and verification methods.*

---

## 4. Project Planning: Kanban Board

```mermaid
kanban
    title Software Development Tasks
    section Backlog
      User Login Feature : 5
      Database Schema Design : 3
    section In Progress
      API Development : 2
    section Testing
      Unit Testing : 4
    section Done
      Project Kickoff : 1
```

*Visualizes task progress in an agile workflow.*

---

## 5. Timeline Planning: Gantt Chart

```mermaid
gantt
    title Software Development Timeline
    dateFormat  YYYY-MM-DD
    section Planning
    Kickoff            :done,    kickoff, 2025-07-01, 3d
    Requirements       :active,  reqs, 2025-07-04, 7d
    section Design
    Architecture       :         arch, after reqs, 5d
    System Design      :         design, after arch, 7d
    section Implementation
    Coding             :         coding, after design, 15d
    Testing            :         testing, after coding, 10d
    Deployment         :         deploy, after testing, 3d
```

*Shows timeline, durations, and dependencies.*

---

## 6. System Architecture: Flowchart

```mermaid
flowchart TB
    Client[Client Application] -->|HTTP Requests| API[API Gateway]
    API --> Auth[Authentication Service]
    API --> Data[Database]
    API --> Logic[Business Logic]
```

*Communicates system components and interactions.*

---

## 7. System Design: Class Diagram

```mermaid
classDiagram
    class User {
        +String id
        +String name
        +login()
        +logout()
    }
    class Order {
        +int orderId
        +date orderDate
        +calculateTotal()
    }
    User "1" --> "*" Order : places
```

*Models data objects and relationships.*

---

## 8. Workflow Design: Flowchart

```mermaid
flowchart TD
    Start --> Input[Enter credentials]
    Input --> Validate{Valid?}
    Validate -- Yes --> Success[Grant access]
    Validate -- No --> Error[Show error message]
    Error --> Input
```

*Visualizes decision points and process loops.*

---

## 9. Interaction Design: Sequence Diagram

```mermaid
sequenceDiagram
    participant User
    participant UI
    participant Server
    participant DB

    User->>UI: Submit login form
    UI->>Server: POST /login
    Server->>DB: Query user credentials
    DB-->>Server: Return data
    Server-->>UI: Login success/fail
    UI-->>User: Show result
```

*Models message flow over time between components.*

---

## 10. Summary & Best Practices

* Match diagram type to purpose for clarity.
* Use mindmaps & requirements early.
* Kanban and Gantt for planning.
* Flowcharts & class diagrams for design.
* Sequence diagrams for interaction flows.
* Embed Mermaid in docs for maintainability.
* Keep diagrams simple, clear, and modular.

---

## 11. Q\&A
