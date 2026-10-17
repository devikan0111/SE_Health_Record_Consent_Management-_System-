# Software Engineering Lab Submissions

Software Engineering project

## Student Details

- **Name:** Devika N
- **SRN:** PES1UG24AM080
- **Section:** B
- **Course:** Software Engineering

## Problem Statement
(For Labs 1-3)

**Problem Statement #13: Healthcare & Telemedicine**

A patient-centric electronic health data gateway that lets patients explicitly
manage access to their medical history. Patients give granular, time-bound
consent to authorized healthcare personnel (clinic doctors, diagnostic
laboratories, consulting doctors), can revoke consent before it expires, and
can grant access to multiple records in a single action. Doctors must
authenticate with Multi-Factor Authentication (MFA) before viewing records, and
every consent, revocation and access event is kept in an audit trail.

**Actors:** Patient, Clinic Doctor, Clinic Administrator

## Lab Submissions

| Lab | Topic | Location |
| --- | --- | --- |
| Lab 1 | Requirements Engineering & UML Use-Case Modelling | `PES1UG24AM080_LAB1.pdf` |
| Lab 2 | Agile Backlog Creation & Sprint Simulation in Jira | `PES1UG24AM080_LAB2 .pdf` |
| Lab 3 | Component Modelling & Architectural Pattern Selection | `PES1UG24AM080_Lab3.pdf`, `PES1UG24AM080_Lab3_Component_Diagram.png` |
| Lab 4 | Vibe Coding with an LLM (Blackjack) | [`Lab4/`](Lab4) |

## Lab 1: Requirements Engineering & UML Use-Case Modelling

Identified the key functions and constraints, wrote verifiable requirements, and
modelled the system with a UML use-case diagram (actors, use cases, include and
extend relationships). The core use case documented is **UC-02: Revoke Access**.

**Functional requirements**
- FR-001: Grant time-bounded access to specific diagnostic records
- FR-002: Revoke previously granted consent before expiry
- FR-003: Require MFA before record access
- FR-004: Grant multiple records in a single consent action
- FR-005: Let Clinic Administrators view a read-only audit trail

**Non-functional requirements**
- NFR-001: Append-only audit trail for consent and access events
- NFR-002: Encrypt records and consent information at rest and in transit

## Lab 2: Agile Backlog & Sprint Simulation (Jira)

Converted the Lab 1 requirements into 3 epics and 7 user stories, estimated them
with Fibonacci story points, and ran two sprints in Jira with burndown charts.

- **Epics:** Patient Consent & Access Control, Doctor Authentication & Access
  Management, Audit Trail & System Security
- **Sprint 1 (13 points):** consent granting and revocation, doctor MFA
- **Sprint 2 (16 points):** multi-record grants, audit log viewer, audit
  logging, encryption

## Lab 3: Component Modelling & Architectural Pattern Selection

Chose a **three-layer (Layered) architecture** and modelled it as a UML
component diagram.

- **Presentation layer:** User Interface
- **Business layer:** Consent Manager, Authentication, Audit Logger,
  Notification Service
- **Data layer:** Consent & Health Record Database, Audit Log Database

Layered architecture gives a single enforcement point for consent rules, strong
consistency for instant revocation and auditing, and clear security boundaries.
See `PES1UG24AM080_Lab3.pdf` for the report and the full reasoning, and
`PES1UG24AM080_Lab3_Component_Diagram.png` for the component diagram.

## Lab 4: Vibe Coding with an LLM (Blackjack)

Used an LLM as a coding assistant to fix and extend a terminal Blackjack game
in Python, one task at a time with a separate commit for each.

1. Fixed the Ace scoring bug (Aces count as 1 when 11 would bust)
2. Round resolution (blackjack, bust, dealer draws to 17, ties)
3. Chips and betting (validated bets, 3:2 blackjack payout, game over at 0)
4. Feedback and robustness (draw messages, input validation, empty deck)

The [`Lab4/`](Lab4) folder has the before and after videos, the updated code and
the exported chat history. Code repo with the per-task commits:
https://github.com/devikan0111/SE_18_blackjack
