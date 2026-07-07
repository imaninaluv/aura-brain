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

---

# Schema Overview

The Account Context Schema represents a single connected Threads account within Aura AI.

Every business object created throughout the platform belongs to exactly one Account Context.

This schema acts as the root business context for all creator activities.

```
Aura Account
        │
        ▼
Account Context
        │
        ├──────────────┬──────────────┬──────────────┬──────────────┐
        ▼              ▼              ▼              ▼              ▼
     Threads        Planner        Drafts         Replies        Stats
```

The Account Context itself does not store business content.

Instead, it provides the ownership boundary for every business object created by the creator.

---

# Core Properties

Each Account Context contains the minimum information required to identify and operate a connected Threads account.

Core properties include:

| Property | Description |
|----------|-------------|
| Context ID | Unique identifier for the Account Context. |
| Aura User ID | Owner of the Account Context. |
| Threads Account ID | Connected Threads account identifier. |
| Threads Username | Current Threads username. |
| Display Name | Current Threads display name. |
| Profile Image | Threads profile picture. |
| Connection Status | Current connection state with Threads. |
| Active Status | Indicates whether this is the active working context. |
| Connected At | Date and time the account was connected. |
| Last Active At | Last time this context was used inside Aura AI. |

These properties identify the business workspace without storing feature-specific information.

---

# Relationships

Account Context acts as the parent business object for nearly every creator activity.

Relationship overview:

```
Aura User
        │
        ▼
Account Context
        │
 ┌──────┼────────┬────────┬────────┬────────┐
 ▼      ▼        ▼        ▼        ▼
Thread Draft  Planner  Reply   Stats
                       │
                       ▼
                   Analysis
```

Each relationship follows strict ownership rules.

Examples:

- Every Thread belongs to one Account Context.
- Every Draft belongs to one Account Context.
- Every Planner activity belongs to one Account Context.
- Every Reply belongs to one Account Context.
- Every Stats record belongs to one Account Context.
- Every Analysis record belongs to one Account Context.

Business objects never belong directly to the Aura User.

Instead, they always belong to the currently selected Account Context.

This design allows creators to manage multiple Threads accounts independently while using a single Aura AI account.

---

# Lifecycle

Every Account Context follows a predictable lifecycle from connection to daily usage.

The lifecycle ensures that creators can safely manage multiple Threads accounts while maintaining complete separation between each workspace.

```
Connect Threads Account
            │
            ▼
Create Account Context
            │
            ▼
Ready
            │
            ▼
Set as Active Context
            │
            ▼
Daily Operations
            │
            ├── Write
            ├── Scout
            ├── Planner
            ├── Stats
            │
            ▼
Switch Context
            │
            ▼
Another Account Context Becomes Active
```

An Account Context remains available until the creator removes the connected Threads account from Aura AI.

Removing one Account Context does not affect any other connected account.

---

# Ownership

The Account Context acts as the business owner for every creator activity.

Rather than attaching business objects directly to the Aura User, Aura AI assigns ownership through the active Account Context.

Ownership hierarchy:

```
Aura User
        │
        ▼
Account Context
        │
 ┌──────┼────────┬────────┬────────┬────────┐
 ▼      ▼        ▼        ▼        ▼
Thread Draft  Planner  Reply   Stats
                       │
                       ▼
                   Analysis
```

This ownership model ensures that:

- Drafts remain separated between Threads accounts.
- Planner history remains separated.
- Published Threads remain separated.
- Published Replies remain separated.
- Statistics remain separated.
- AI Analysis history remains separated.

Business data never crosses Account Context boundaries.

---

# Context Switching

Creators may switch between connected Threads accounts at any time through the Account Switcher.

Switching the active Account Context immediately updates the operational workspace across Aura AI.

The following features automatically reflect the newly selected Account Context:

- Home
- Write
- Scout
- Planner
- Stats

Only the active Account Context is visible during normal operation.

Previously active Account Contexts remain unchanged, preserving their own content history, drafts, planner activities, engagement records, and performance data.

Switching contexts never merges, copies, or transfers business data between different Threads accounts.

---

# Business Rules

The Account Context Schema follows strict operational rules to ensure business data remains isolated between connected Threads accounts.

## Rule 1 — One Aura Account, Multiple Account Contexts

A single Aura AI account may own multiple Account Contexts.

Each Account Context represents one connected Threads account.

Multiple Account Contexts may coexist without sharing business data.

---

## Rule 2 — Only One Active Context

Only one Account Context may be active at any given time.

Every creator action performed inside Aura AI belongs to the currently active Account Context.

Business features should never operate across multiple Account Contexts simultaneously.

---

## Rule 3 — Context Isolation

Every Account Context owns its own business workspace.

The following data must always remain isolated:

- Threads
- Drafts
- Planner activities
- Replies
- Statistics
- AI Analysis

Data belonging to one Account Context must never appear inside another Account Context.

---

## Rule 4 — Context-Aware Operations

Every business operation must determine the active Account Context before execution.

Examples include:

- Generating Threads.
- Generating Replies.
- Saving Drafts.
- Scheduling Posts.
- Publishing Content.
- Viewing Statistics.

Operations should always use the currently active Account Context as their business owner.

---

## Rule 5 — Context Persistence

Switching between Account Contexts should never modify historical business data.

Each Account Context preserves its own:

- Content history.
- Planner history.
- Drafts.
- Engagement history.
- Performance history.

Returning to a previously used Account Context restores its complete workspace exactly as it was left.

---

# Validation Rules

Before any business operation begins, Aura AI should validate the current Account Context.

Validation includes:

- An active Account Context exists.
- The connected Threads account remains available.
- The Account Context belongs to the authenticated Aura User.
- The Account Context is eligible to perform the requested operation.

If validation fails, no business operation should continue until the issue has been resolved.

These validation rules protect business ownership, prevent cross-account data leakage, and maintain the integrity of every creator workspace.

---

# Business Examples

The following examples demonstrate how Account Context behaves during normal platform usage.

### Example 1 — Multiple Connected Threads Accounts

```
Aura Account
        │
        ├──────────────┐
        │              │
        ▼              ▼
@brand_a         @personal
(Account A)      (Account B)
```

Both Account Contexts belong to the same Aura AI account.

Each maintains its own:

- Threads
- Drafts
- Planner
- Replies
- Statistics
- Analysis

No business data is shared between the two workspaces.

---

### Example 2 — Switching Account Context

Current Active Context:

```
@brand_a
```

Creator switches to:

```
@personal
```

Aura AI immediately updates:

- Home
- Write
- Scout
- Planner
- Stats

The creator now works entirely within the newly selected Account Context.

Historical data belonging to `@brand_a` remains unchanged.

---

### Example 3 — Business Ownership

Creator generates:

- 3 new Threads
- 5 published Replies
- 2 Drafts

while working inside:

```
@brand_a
```

Every business object created during that session belongs to the Account Context for `@brand_a`.

Switching to another Account Context does not transfer, duplicate, or expose those business objects.

---

# Design Rationale

Account Context exists to separate creator identity from platform identity.

A creator owns one Aura AI account,

but may manage multiple independent Threads accounts.

By introducing Account Context as the operational boundary,

Aura AI preserves complete separation between different brands,

businesses,

or personal identities without requiring multiple Aura AI accounts.

This design also simplifies future platform expansion.

Additional social platforms can introduce their own Account Contexts while preserving the same ownership model and business architecture.

---

# Final Statement

The Account Context Schema establishes the operational foundation upon which every creator workflow is built.

It defines the active workspace,

owns every business object created within that workspace,

and ensures complete isolation between connected Threads accounts.

As Aura AI evolves,

Account Context remains the primary business boundary that allows creators to manage multiple online identities safely,

consistently,

and independently from a single Aura AI account.
