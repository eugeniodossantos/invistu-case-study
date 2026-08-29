# Architecture — INVISTU

## Architectural style

INVISTU follows an **API-first modular monolith** approach. The goal is to keep the initial system operationally simple while preserving strong domain boundaries that can evolve independently as the product grows.

## Main layers

```text
Clients
├── Web: Next.js + TypeScript
└── Mobile: React Native + Expo + TypeScript
          |
          v
Application API
└── NestJS + TypeScript
    ├── Identity & Account
    ├── Workspaces
    ├── Financial Diagnosis
    ├── Income / Expenses
    ├── Debts
    ├── Savings / Emergency Fund
    ├── Goals / Simulations
    ├── Advice / Insights
    ├── Subscription
    └── Security / Audit
          |
    ---------------------
    |                   |
PostgreSQL            Redis
```

## Why API-first

- Web and mobile clients can consume the same business API.
- Business rules stay outside presentation layers.
- New clients or integrations can be added without duplicating the domain model.
- Authentication, authorization and audit policies can be centralized.

## Why a modular monolith first

- Lower infrastructure complexity during early product stages.
- Easier transactional consistency across related financial domains.
- Clear module boundaries without premature microservice overhead.
- Easier testing, deployment and refactoring while product-market requirements evolve.

## Workspace model

The platform supports distinct financial contexts:

- Personal workspace
- Family workspace
- Company workspace

Users interact with the appropriate workspace without mixing financial data or permissions between contexts.

## Security principles

- Strong identity boundaries
- Workspace-scoped authorization
- Session / device visibility
- Auditability of sensitive actions
- Separation of public API contracts from internal implementation
- No credentials or production security configuration in this repository
