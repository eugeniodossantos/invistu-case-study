# INVISTU — Financial Management SaaS Case Study

Technical case study of **INVISTU**, a financial management and financial-education platform designed for personal, family and business use.

> **Status:** Active development / pre-production.

## Product vision

INVISTU is designed to go beyond simple expense tracking. The platform observes the user's financial reality, organizes financial information and supports better decisions through planning, priorities, savings, goals, risk awareness and proactive guidance.

## Problems addressed

- Fragmented visibility over income, expenses and financial commitments.
- Difficulty understanding whether a financial decision is sustainable.
- Lack of structured planning for savings and emergency reserves.
- Weak follow-up of debts, goals and recurring responsibilities.
- Separation between personal, family and business financial contexts.
- Limited financial education inside traditional expense-tracking tools.
- Need for a secure, centralized financial workspace.

## Core capabilities

- Financial onboarding and initial diagnosis
- Income and additional-income management
- Expense tracking and categorization
- Debt management
- Priorities and financial planning
- Savings and emergency fund
- Financial reserves
- Goals and simulations
- Unexpected-expense planning
- Reports and financial insights
- Proactive financial guidance
- Personal, family and company workspaces
- Account security and device/session management

## Technology stack

| Layer | Technology |
|---|---|
| Web | Next.js + TypeScript |
| Mobile | React Native + Expo + TypeScript |
| Backend / API | NestJS + TypeScript |
| Database | PostgreSQL |
| Cache / fast state | Redis |
| Architecture | API-first, modular monolith |
| Version control | Git / GitHub |

## Architecture

```text
Web App (Next.js)          Mobile App (React Native)
        |                           |
        +------------+--------------+
                     |
                     v
              NestJS REST API
                     |
          -----------------------
          |                     |
      PostgreSQL              Redis
          |
          v
 Financial domain / workspaces / audit
```

See [`docs/architecture.md`](docs/architecture.md) for more detail.

## Data model

The public case study documents only high-level financial domains. It does not expose the production schema, sensitive security rules or private implementation details.

Conceptual domains include users, workspaces, memberships, income, expenses, debts, savings, emergency funds, goals, subscriptions, devices and audit events.

See [`docs/database.md`](docs/database.md).

## My role

I am responsible for product definition and Full-Stack development, including requirements analysis, UX flow, architecture, backend/API design, data modelling, frontend implementation and the evolution of business rules.

## Development timeline

The product is under active development. A final commercial delivery duration is therefore not presented as a completed project timeline.

## Screenshots

Approved non-sensitive screens will be maintained in [`assets/screenshots/`](assets/screenshots/).

## Source code policy

This repository contains **documentation and portfolio material only**. The INVISTU production source code, credentials, private business rules, infrastructure details and sensitive security mechanisms are not published.

---

**Developer:** Eugénio Fernandes dos Santos  
**GitHub:** https://github.com/eugeniodossantos
