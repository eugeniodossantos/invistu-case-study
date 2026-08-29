# Data Model — INVISTU

This document describes the **conceptual data model** used to explain the product architecture without publishing the private production schema.

## Main domains

- **User** — authenticated person using the platform.
- **Workspace** — personal, family or company financial context.
- **Membership** — relationship between a user and a workspace, including access level.
- **Income** — recurring or additional financial inflows.
- **Expense** — financial outflow, category and date information.
- **Debt** — liability, payment status and planning information.
- **Savings** — amounts intentionally reserved for future use.
- **Emergency Fund** — protected reserve for unexpected events.
- **Goal** — financial objective with target and progress.
- **Simulation** — scenario used to evaluate a possible financial decision.
- **Subscription** — plan and commercial lifecycle of an account/workspace.
- **Device / Session** — security visibility over authenticated access.
- **Audit Event** — trace of important security and financial actions.

## Conceptual relationship overview

```text
User * --- * Workspace
          via Membership

Workspace 1 --- * Income
Workspace 1 --- * Expense
Workspace 1 --- * Debt
Workspace 1 --- * Savings
Workspace 1 --- * Goal
Workspace 1 --- * Simulation
Workspace 1 --- * Audit Event

User 1 --- * Device / Session
Workspace 1 --- 0..1 Subscription
```

## Database technology

**PostgreSQL** is the primary relational database. Relational storage was selected because financial domains require strong consistency, structured relationships, transactional operations and reliable reporting.

## Redis

Redis is used as a supporting fast-state / cache layer where low-latency access or temporary application state is appropriate. It is not treated as the authoritative source of financial records.

## Privacy and security

This public repository intentionally excludes:

- Exact table names and production migrations
- Credentials and connection strings
- Identity-verification internals
- Anti-abuse implementation details
- Encryption secrets
- Production data
- Private financial algorithms
