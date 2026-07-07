# User Profile Schema

Version: 1.0
Status: Locked
Last Updated: 2026-07-07

---

# Purpose

The User Profile Schema defines the creator's personal preferences within Aura AI.

Unlike the Account Context, which represents the currently active Threads workspace, the User Profile represents the creator's preferred way of using the platform.

Its purpose is to reduce repetitive configuration by remembering creator preferences across future sessions while preserving complete creator control.

---

# Definition

A User Profile is the persistent personal profile associated with a single Aura AI account.

It stores creator preferences that influence the default behaviour of the platform without affecting the creator's content, planner, statistics, or business history.

The User Profile exists independently from any individual Threads account.

Regardless of how many Account Contexts a creator connects, only one User Profile exists for each Aura AI account.

---

# Scope

The User Profile Schema provides default preferences that may be shared across every Account Context.

These preferences may be used by:

- Home
- Write
- Scout
- Planner
- Stats

Business features may use the User Profile to pre-fill commonly selected options, reducing unnecessary repetitive input from the creator.

The User Profile does not own business objects such as Threads, Drafts, Replies, Planner activities, Statistics, or Analysis.

Those business objects belong to the active Account Context.

---

# Core Concept

Aura AI distinguishes between who the creator is and where the creator is working.

```
Aura Account
        │
        ├──────────────┐
        │              │
        ▼              ▼
User Profile     Account Context
(Creator)        (Workspace)

        │              │
        │              ├── Threads
        │              ├── Drafts
        │              ├── Planner
        │              ├── Replies
        │              ├── Stats
        │              └── Analysis
        │
        ├── Preferred Language
        ├── Preferred Tone
        ├── Preferred Writing Mode
        ├── Preferred Word Length
        ├── Default Product Link
        └── Link in Bio Preference
```

The User Profile remembers how the creator prefers to use Aura AI.

It does not determine which Threads account is active, nor does it own operational business data.

Instead, it provides consistent creator preferences that help reduce repetitive decisions throughout the platform.


---

# Schema Overview

The User Profile Schema stores creator preferences that personalise the Aura AI experience.

Unlike business objects, the User Profile does not contain operational data.

Instead, it provides reusable defaults that reduce repetitive configuration across the platform.

These preferences may evolve over time as the creator changes how they use Aura AI.

---

# Core Properties

Each User Profile contains creator-level preferences that remain available regardless of which Account Context is currently active.

Core properties include:

| Property | Description |
|----------|-------------|
| User Profile ID | Unique identifier for the User Profile. |
| Aura User ID | Owner of the User Profile. |
| Preferred Language | Default language used during content generation. |
| Preferred Tone | Creator's commonly selected writing tone. |
| Preferred Writing Mode | Default writing mode used in Write. |
| Preferred Word Length | Commonly selected thread length. |
| Default Product Link | Product or landing page used most frequently. |
| Link in Bio Preference | Default state for the "Link in Bio" option. |
| Last Updated | Date and time the profile preferences were last modified. |

These properties represent creator preferences rather than business activities.

---

# Relationships

The User Profile supports multiple business features by providing default values during creator workflows.

Relationship overview:

```
Aura User
        │
        ├──────────────┐
        ▼              ▼
User Profile     Account Context
        │              │
        │              ├── Thread
        │              ├── Draft
        │              ├── Planner
        │              ├── Reply
        │              ├── Stats
        │              └── Analysis
        │
        ├── Home
        ├── Write
        ├── Scout
        ├── Planner
        └── Stats
```

The User Profile provides preference data to business features but does not own their business objects.

For example:

- Write uses preferred language as the default selection.
- Write uses the preferred writing mode when opening a new session.
- Default Product Link may automatically populate the product link field.
- Frequently used creator preferences remain available across every Account Context.

Business history always belongs to the Account Context.

Creator preferences always belong to the User Profile.


---

# Lifecycle

A User Profile is created automatically when a creator registers a new Aura AI account.

Unlike business objects, the User Profile exists throughout the lifetime of the Aura AI account and continuously evolves as creator preferences change.

The typical lifecycle is:

```
Create Aura Account
          │
          ▼
Create User Profile
          │
          ▼
Initial Preferences
          │
          ▼
Creator Uses Aura AI
          │
          ▼
Preferences Update Automatically
          │
          ▼
Continuous Personalisation
```

The User Profile remains persistent across every login session and every connected Account Context.

Changing or removing an Account Context never removes or resets the User Profile.

---

# Ownership

The User Profile belongs directly to the Aura User.

Ownership hierarchy:

```
Aura User
      │
      ├──────────────┐
      ▼              ▼
User Profile    Account Context(s)
                     │
                     ├── Thread
                     ├── Draft
                     ├── Planner
                     ├── Reply
                     ├── Stats
                     └── Analysis
```

Unlike Account Context, the User Profile does not own business activities.

Instead, it owns creator preferences that help personalise future experiences throughout Aura AI.

---

# Preference Evolution

Creator preferences are expected to evolve naturally over time.

Aura AI should remember preferences based on the creator's most recent or most frequently selected options.

Examples include:

- Preferred Language
- Preferred Writing Mode
- Preferred Tone
- Preferred Word Length
- Default Product Link
- Link in Bio Preference

Whenever a creator intentionally changes one of these preferences, the User Profile should update accordingly.

Future sessions should automatically present these updated preferences as the default selections, reducing repetitive configuration while preserving full creator control.

Preference updates never modify previously generated Threads, Drafts, Planner activities, Replies, Statistics, or Analysis records.

---

# Business Rules

The User Profile Schema follows a set of rules that ensure creator preferences remain consistent while preserving creator control.

## Rule 1 — One User Profile Per Aura Account

Each Aura AI account owns exactly one User Profile.

The User Profile remains shared across every connected Account Context belonging to the same Aura AI account.

---

## Rule 2 — Preferences Are Persistent

Creator preferences should persist between sessions.

When the creator returns to Aura AI, previously saved preferences should automatically become the default selections where applicable.

Persistence reduces repetitive configuration while keeping the workflow familiar.

---

## Rule 3 — Creator Preferences Always Win

The User Profile should only store preferences intentionally chosen by the creator.

Aura AI must never invent, overwrite, or assume creator preferences without a direct creator action.

The creator always remains in control of their personal defaults.

---

## Rule 4 — Preferences Never Modify Business Data

Updating the User Profile should never change existing business objects.

Changing preferences must not affect:

- Previously generated Threads
- Saved Drafts
- Planner activities
- Published Replies
- Statistics
- Analysis history

Profile updates only influence future creator workflows.

---

## Rule 5 — Shared Across Every Account Context

All connected Account Contexts should reference the same User Profile.

Changing a preference once makes it available throughout Aura AI, regardless of which Threads account is currently active.

This creates a consistent creator experience while maintaining complete separation between operational business data.

---

# Validation Rules

Before applying User Profile preferences, Aura AI should validate that:

- A valid User Profile exists for the authenticated Aura User.
- The requested preference is supported by the platform.
- Preference values remain valid after platform updates.
- Preference changes originate from the authenticated creator.

If validation fails, Aura AI should safely fall back to the platform's default settings without interrupting the creator's workflow.

These validation rules ensure creator preferences remain reliable, secure, and consistent across every session.

---

# Business Examples

The following examples demonstrate how the User Profile behaves during normal platform usage.

### Example 1 — Remembering Creator Preferences

A creator opens the Write feature and selects:

- Language: English
- Writing Mode: Educational
- Tone: Professional
- Word Length: Medium

After generating content, these selections become the creator's preferred defaults.

The next time the creator opens Write, Aura AI automatically pre-selects these values, reducing repetitive configuration.

---

### Example 2 — Updating Preferences

A creator decides to switch from:

```
Professional
```

to

```
Casual
```

for future content.

The User Profile updates the preferred tone.

Future Write sessions use **Casual** as the default selection.

Previously generated Threads, Drafts, Planner activities, Replies, and Statistics remain unchanged.

---

### Example 3 — Multiple Account Contexts

A creator manages two connected Threads accounts:

- @brand_a
- @personal

Both Account Contexts reference the same User Profile.

Regardless of which Account Context is active, Aura AI continues to use the creator's preferred:

- Language
- Writing Mode
- Tone
- Word Length
- Product Link
- Link in Bio preference

Only business data changes between Account Contexts.

Creator preferences remain consistent.

---

# Design Rationale

The User Profile exists to eliminate repetitive configuration while preserving complete creator control.

Instead of asking creators to repeatedly configure the same preferences, Aura AI remembers the options they intentionally choose and reuses them as future defaults.

This approach supports the platform's UX philosophy of reducing unnecessary decisions without reducing creator flexibility.

By separating creator preferences from operational business data, Aura AI maintains a clear distinction between:

- **Who the creator is** (User Profile)
- **Where the creator is working** (Account Context)
- **What the creator creates** (Business Schemas)

This separation keeps the platform scalable, predictable, and easy to maintain.

---

# Final Statement

The User Profile Schema represents the creator's personal preferences within Aura AI.

It provides a consistent and personalised experience across every session while remaining independent from operational business data.

As Aura AI evolves, the User Profile continues to simplify creator workflows by remembering preferences, reducing repetitive configuration, and ensuring every new session begins in a familiar and creator-controlled environment.
