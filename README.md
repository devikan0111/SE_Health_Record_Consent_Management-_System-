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
| Lab 4 | Vibe Coding with an LLM (Blackjack) | [`Lab4/`](https://github.com/devikan0111/SE_18_blackjack) |
| Lab 5 | Static Code Analysis (Supplier Orders) | [`L5_18_supplier_orders`](https://github.com/devikan0111/L5_18_supplier_orders) |
| Lab 6 | Code and Branch Coverage (ATM Withdrawal) | [`L6_L7_18_atm_withdrawal_SE/Lab 6`](https://github.com/devikan0111/L6_L7_18_atm_withdrawal_SE/tree/main/Lab%206) |
| Lab 7 | Fuzz Testing with Hypothesis (ATM Withdrawal) | [`L6_L7_18_atm_withdrawal_SE/Lab 7`](https://github.com/devikan0111/L6_L7_18_atm_withdrawal_SE/tree/main/Lab%207) |

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

The repository with the per-task commits:
https://github.com/devikan0111/SE_18_blackjack

## Lab 5: Static Code Analysis (Supplier Orders)

Used three static analysis tools (Pylint, Flake8 and Bandit) to find quality,
style and security problems in a supplier purchase order tracker. The issues were
documented in a table with line numbers, descriptions and fix approaches, and
then fixed.

| Tool | Before | After |
| --- | --- | --- |
| Pylint | 2.41 / 10 | 10.00 / 10 |
| Bandit | 1 High, 1 Medium, 1 Low | 0 issues |
| Flake8 | 4 findings | 0 findings |

**Main fixes**
- Removed a shell command built from input (command injection, Bandit B605)
- Replaced a string-formatted SQL query with a parameterised query (SQL injection, B608)
- Replaced a silent `except Exception: pass` with specific error handling and logging
- Removed global state, unused arguments and renamed functions to snake_case
- Added docstrings, a `__main__` guard, and split long lines

Repository link: https://github.com/devikan0111/L5_18_supplier_orders

## Lab 6: Code and Branch Coverage (ATM Withdrawal)

Measured and improved test coverage of an ATM withdrawal module using
`coverage` and `pytest`. The module has three functions: `withdraw` (account
type, amount validation, daily limits, other-bank fees, balance check),
`pin_check` (ok, retry, card blocked) and `note_breakup` (500, 200 and 100
notes).

| Stage | Tests | Coverage |
| --- | --- | --- |
| Starter tests | 2 | 38% line |
| `CodeCoverageTest_atm_withdrawal.py` | 13 | 100% line |
| `BranchCoverageTest_atm_withdrawal.py` | 31 | 100% branch (22 of 22 branches) |

**Line coverage vs branch coverage.** The 13 line-coverage tests executed every
line, but branch coverage on the same tests still missed one branch (an
other-bank withdrawal of 10000 or less). The branch tests close that gap and add
edge cases: zero and negative amounts, amounts that are not multiples of 100,
exact daily-limit boundaries, balance exactly equal to amount plus fee,
insufficient funds caused only by the fee, a correct PIN after the card is
blocked, and note breakups with remainders of 0, 100, 200, 300 and 400.

**Deliverables:** the two test files, terminal screenshots of both coverage
reports, and two separate commits (one for code coverage, one for branch
coverage).

Repository link: https://github.com/devikan0111/L6_L7_18_atm_withdrawal_SE/tree/main/Lab%206

## Lab 7: Fuzz Testing with Hypothesis (ATM Withdrawal)

Used the Hypothesis property-based testing library to fuzz three text-input
functions in the ATM module (`notes_needed`, `mask_card` and
`average_withdrawal`), found the inputs that crashed them, and fixed them.

Three no-crash tests (using `st.text() | st.none()`) fail if a function raises
any exception, and three correctness tests check that valid input still gives
the right answer.

| Function | Failing input | Error in the original code |
| --- | --- | --- |
| `notes_needed` | empty string | `ValueError` |
| `notes_needed` | `None` | `AttributeError` |
| `mask_card` | empty string | `IndexError` |
| `mask_card` | `None` | `AttributeError` |
| `average_withdrawal` | empty string | `ValueError` |
| `average_withdrawal` | `None` | `AttributeError` |

**Fix:** each function now checks that the input is a string, validates its
format (digits only, or exactly 4 groups of 4 digits for a card number), and
returns `None` for invalid input. The program prints "Invalid input" instead of
crashing.

| Version | Test result |
| --- | --- |
| Original code | 3 failed, 3 passed |
| Fixed code | 6 passed |

**Deliverables:** the fixed `atm_withdrawal.py`, the completed
`test_atm_withdrawal.py`, and a PDF of screenshots
(`PES1UG24AM080_ScreenShots_Lab7.pdf`).

Repository link: https://github.com/devikan0111/L6_L7_18_atm_withdrawal_SE/tree/main/Lab%207
