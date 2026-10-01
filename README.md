# Patient Health Record Consent Management System

**Software Engineering**
## Student Details

- **Name:** Devika N
- **SRN:** PES1UG24AM080
- **Section:** B
- **Course:** Software Engineering 

---

## Problem Statement

### Problem Statement #13 — Healthcare & Telemedicine

### Patient Health Record Consent Management System

The Patient Health Record Consent Management System is a patient-centric electronic health data gateway designed to allow patients to explicitly manage access to their medical history.

The system allows patients to provide **granular and time-bound consent permissions** to authorized healthcare personnel such as:

- Clinic doctors
- Diagnostic laboratories
- Consulting doctors

Patients can control who can access their medical records, specify the records that can be accessed, and define how long the access permission remains valid.

The system also supports revocation of previously granted consent and maintains an audit trail of consent and access-related events.

---

## Problem Context

Healthcare records contain sensitive personal information and therefore require controlled access.

The proposed system focuses on giving patients greater control over their health information by allowing them to:

- Grant access to specific diagnostic records.
- Provide access for a limited period of time.
- Revoke previously granted access before its expiry.
- Control access to multiple records through a single consent action.
- Ensure that clinic doctors authenticate using Multi-Factor Authentication (MFA) before viewing patient records.
- Maintain an audit trail of consent, revocation, and access events.

---

## Main Stakeholders / Actors

The primary actors identified for the system include:

- **Patient**
- **Clinic Doctor**
- **Clinic Administrator**

The patient manages consent permissions, while clinic doctors access records based on valid consent. The clinic administrator can monitor consent and access events through the audit trail.

---

## Lab 1 — Requirements Engineering & UML Use-Case Modelling

### Objective

To identify key functions and constraints from the given healthcare scenario, define clear and verifiable functional and non-functional requirements, and model the system using UML use-case modelling.

### Functional Requirements

The system contains the following functional requirements:

- **FR-001:** Grant time-bounded access to specific diagnostic records.
- **FR-002:** Revoke previously granted consent before expiry.
- **FR-003:** Require Multi-Factor Authentication (MFA) before record access.
- **FR-004:** Allow multiple diagnostic records to be granted in a single consent action.
- **FR-005:** Allow Clinic Administrators to view a read-only audit trail.

### Non-Functional Requirements

- **NFR-001:** Maintain an append-only audit trail for consent and access events.
- **NFR-002:** Encrypt patient health records and consent information at rest and in transit.

### UML Use-Case Model

The UML use-case model represents the actors, primary system functions, and relationships between use cases.

The model includes:

- Actors
- Primary use cases
- include and extend relationships

### Use-Case Flow

The core use case documented in Lab 1 is:

**UC-02: Revoke Access**

The flow includes:

- Preconditions
- Postconditions
- Main Success Scenario
- Alternate Flow 

---

## Lab 2 — Agile Backlog Creation & Sprint Simulation in Jira

### Objective

To convert the functional requirements identified in Lab 1 into Agile backlog items, create Epics and User Stories, prioritize and estimate them using Fibonacci story points, simulate sprints in Jira, and analyze sprint progress through Burndown charts.

### Epics
- **HRCM-1:** Patient Consent & Access Control
- **HRCM-2:** Doctor Authentication & Access Management
- **HRCM-3:** Audit Trail & System Security

### User Stories 
- **HRCM-4:** Time-Bounded Access Grant (5 Story Points, High Priority)
- **HRCM-5:** Multi-Record Batch Grant (3 Story Points, Medium Priority)
- **HRCM-6:** Instant Consent Revocation (5 Story Points, High Priority)
- **HRCM-7:** : Doctor Multi-Factor Authentication (3 Story Points, High Priority)
- **HRCM-8:** Read-Only Audit Log Viewer (3 Story Points, Medium Priority)
- **HRCM-9:** Append-Only Audit Logging (5 Story Points, High Priority)
- **HRCM-10:** Encrypt Data (5 Story Points, High Priority)

### Sprint Execution Summary
- **Sprint 1 (13 Story Points):** Focused on core user consent granting/revocation and doctor MFA setup. All stories transitioned from To Do → In Progress → Done successfully.
- **Sprint 2 (16 Story Points):** Focused on multi-record consent actions, administrator audit capabilities, and end-to-end data encryption. All stories completed on schedule.

### Deliverables & Artifacts
- `PES1UG24AM080_LAB1.pdf`: Lab 1 Requirements Engineering & UML Use-Case Documentation
- `PES1UG24AM080_LAB2.pdf`: Lab 2 Jira Project Artifacts, Sprint Boards and Burndown Charts
