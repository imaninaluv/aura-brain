# Account Context Schema

Version: 1.0
Status: Locked
Last Updated: 2026-07-07

---

# Purpose

The Account Context Schema defines the active operating environment for Aura AI.

It establishes which connected Threads account the platform is currently working with and provides the shared business context used across every feature.

Rather than representing the creator themselves, the Account Context represents the identity under which Aura AI performs all business operations.

---

# Definition

An Account Context is a dedicated workspace for a single connected Threads account.

Each Aura AI account may contain multiple Account Contexts, allowing creators to manage different Threads accounts independently from one another.

Only one Account Context can be active at any given time.

Every business operation performed within Aura AI belongs to the currently active Account Context.

---

# Scope

The Account Context Schema applies to every creator-facing feature within Aura AI.

This includes:

- Home
- Write
- Scout
- Planner
- Stats

Each feature should always operate using the currently active Account Context.

No feature should access data belonging to another Account Context unless the creator explicitly switches accounts.

---

# Core Concept

Aura AI separates the creator's identity from the social media accounts they manage.

```
Aura Account
        │
        ├──────────────┐
        │              │
        ▼              ▼
Account Context A   Account Context B
(@brand_a)          (@personal)

        │              │
        ▼              ▼
Own Data         Own Data
Own Planner      Own Planner
Own Drafts       Own Drafts
Own Stats        Own Stats
Own Replies      Own Replies
```

Each Account Context behaves as an independent business workspace.

Although multiple contexts belong to the same Aura AI account, they never share operational data.

This separation ensures every Threads account maintains its own content history, planning activities, engagement records, and performance metrics while remaining accessible through a single Aura AI account.
