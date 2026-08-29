# Technical Challenges — INVISTU

## 1. Complex financial rules without complex UX

Financial products naturally accumulate rules around income, expenses, debt, reserves, goals and risk. Exposing all of that directly would create a confusing interface.

**Approach:** keep business logic in the API/domain layer while presenting users with guided flows, prioritized information and clear next actions.

## 2. Multiple financial contexts

The same user may need personal, family and business financial management without mixing data or permissions.

**Approach:** use workspace-scoped data and memberships so each financial context remains isolated while the user can switch between them.

## 3. Shared web and mobile business logic

Duplicating business rules in separate web and mobile applications would increase inconsistency and maintenance cost.

**Approach:** use an API-first backend so Next.js and React Native clients consume the same business rules and financial model.

## 4. Financial consistency and auditability

Financial records require reliable relationships and traceability.

**Approach:** use PostgreSQL as the authoritative transactional data store and keep audit/security concerns as first-class architectural domains.

## 5. Product evolution without premature infrastructure complexity

The product needs strong modularity but does not initially require independent distributed services for every domain.

**Approach:** start with a modular monolith in NestJS, preserving clear domain boundaries that can be extracted later if scale or operations justify it.

## 6. Proactive guidance

The product is intended to do more than display historical transactions; it must help users identify risky or counterproductive decisions.

**Approach:** structure financial data so guidance and warnings can be generated from the user's current obligations, priorities, reserves and goals without embedding presentation-specific logic into the core domain.
