# State Management

Version: 1.0
Status: Locked
Last Updated: 2026-07-07

---

# Purpose

State Management defines how Aura AI manages information that changes during application usage.

Its purpose is ensuring every feature maintains a consistent, predictable, and reliable application state while preserving a seamless creator experience.

State Management governs how information is created,

updated,

shared,

and removed throughout the platform.

---

# Scope

State Management applies to all runtime states within Aura AI.

Examples include:

- User sessions.
- Active connected account.
- Current feature state.
- Draft state.
- Planner state.
- AI execution state.
- Platform connection state.
- User interface state.

Persistent business data remains the responsibility of the Database Architecture.

State Management focuses only on information required while the application is actively running.

---

# Core Principle

State represents the current condition of the application.

State is temporary.

Business data is persistent.

State may reference persistent business data,

but it should never replace the database as the source of truth.

This separation ensures that runtime behaviour remains independent from long-term data storage.

---

# State Philosophy

Aura AI treats state as a runtime representation of the current application experience.

Business features manage only the states necessary for their responsibilities,

while persistent information remains safely stored within the database.

By separating runtime state,

business data,

and AI execution,

Aura AI maintains a system that is:

- Predictable.
- Responsive.
- Consistent.
- Maintainable.

Every state should exist for a clear purpose and disappear when it is no longer required.


---

# High-Level State Architecture

Aura AI organises runtime information into multiple state categories.

Each category represents a different aspect of the application's runtime behaviour.

```
Platform State

│

├── Session State

├── Active Account State

├── Feature State

├── Execution State

├── Connection State

└── Interface State
```

Each state category has a clearly defined responsibility and lifecycle.

Together,

they provide a consistent runtime experience without affecting persistent business data.

---

# Platform State

Platform State represents information shared across the entire application.

Examples include:

- Current user session.
- Current active connected account.
- Global application status.

Platform State provides the foundation upon which all other runtime states operate.

---

# Feature State

Each business feature manages its own runtime state independently.

Examples include:

- Current draft.
- Current planner view.
- Current scout session.
- Current analytics view.

Feature states remain isolated from one another while sharing the same Platform State.

---

# Execution State

Execution State represents temporary operations currently being performed.

Examples include:

- AI generation.
- Publishing requests.
- Content scheduling.
- Data synchronisation.

Execution State exists only while an operation is active.

Once completed,

its state is removed or replaced by the resulting business data.

---

# Interface State

Interface State represents the current presentation of the application.

Examples include:

- Active screen.
- Expanded planner date.
- Selected navigation item.
- Open dialogs.
- Current calendar view.

Interface State affects only the user experience and never changes business ownership.

---

# State Hierarchy

Higher-level states provide context for lower-level states.

For example,

the Active Account determines which business data becomes available,

while Feature States manage only the runtime behaviour within that active context.

This hierarchy maintains predictable application behaviour while preventing unnecessary dependencies between unrelated states.


---

# State Categories

Aura AI separates runtime information into specialised state categories.

Each category has a clearly defined purpose,

lifecycle,

and responsibility.

State categories remain independent while sharing the same application context.

---

# Session State

Session State represents the current platform session.

Examples include:

- Authentication status.
- Current Aura User.
- Session validity.

Session State exists from user sign-in until the session ends.

---

# Active Account State

Active Account State represents the currently selected connected Threads account.

Examples include:

- Current connected account.
- Account switching status.
- Connected account context.

All business features operate using the current Active Account.

Changing the Active Account updates the runtime context for Write,

Planner,

Scout,

and Stats without affecting business data owned by other connected accounts.

---

# Feature State

Each feature manages its own runtime information independently.

Examples include:

Write

- Current draft.
- Writing mode.
- Editor state.

Planner

- Current calendar.
- Selected date.
- Expanded activity list.

Scout

- Current discovery session.
- Selected post.
- Current reply generation.

Stats

- Current analytics period.
- Selected metric.
- Current insight view.

Feature States remain isolated from one another while sharing the same Platform State.

---

# Execution State

Execution State represents temporary operations currently in progress.

Examples include:

- AI generation.
- Content publishing.
- Platform communication.
- Data synchronisation.

Execution State exists only during active operations.

Once an operation finishes,

the state is cleared and the resulting business data is handled by its owning feature.

---

# Connection State

Connection State represents the status of external provider communication.

Examples include:

- Connected.
- Connecting.
- Refreshing.
- Disconnected.
- Expired.

Connection State allows Aura AI to manage provider availability independently from business features.

---

# Interface State

Interface State controls the presentation of the application.

Examples include:

- Current screen.
- Selected sidebar item.
- Open dialogs.
- Expanded planner date.
- Current calendar month.

Interface State affects only the user experience and never changes persistent business data.

---

# State Lifecycle

Every state within Aura AI follows a clearly defined lifecycle.

States are created when required,

updated while active,

and removed when they are no longer needed.

This predictable lifecycle ensures consistent runtime behaviour while preventing unnecessary state persistence.

---

# Session Lifecycle

Session State begins when a creator successfully signs in.

```
Signed Out

↓

Signing In

↓

Active Session

↓

Session Expired

↓

Signed Out
```

The current session provides the foundation for all other runtime states.

---

# Active Account Lifecycle

The Active Account changes whenever the creator switches between connected Threads accounts.

```
No Active Account

↓

Select Account

↓

Active Account

↓

Switch Account

↓

New Active Account
```

Changing the Active Account updates the runtime context for every business feature without modifying persistent business data.

---

# Feature Lifecycle

Each feature manages its own independent runtime lifecycle.

Example:

Write

```
Idle

↓

Editing

↓

Auto Saving

↓

Saved

↓

Continue Editing
```

Planner

```
Open Calendar

↓

Select Date

↓

Expand Activities

↓

Close Activities
```

Scout

```
Discover Content

↓

Generate Replies

↓

Select Reply

↓

Publish
```

Feature lifecycles remain independent while sharing the same Platform State.

---

# Execution Lifecycle

Execution State exists only while an operation is running.

```
Idle

↓

Processing

↓

Completed

or

↓

Failed
```

When execution finishes,

the runtime state is removed and the resulting business data is handled by the responsible business feature.

---

# Connection Lifecycle

Connection State reflects the availability of external providers.

```
Disconnected

↓

Connecting

↓

Connected

↓

Refreshing

↓

Connected
```

If communication becomes unavailable,

the Connection State returns to:

```
Disconnected
```

Business features remain isolated from provider-specific connection management.

---

# Lifecycle Consistency

Every runtime state should have:

- A clear starting point.
- A predictable update process.
- A defined completion point.

States should never remain active after their responsibility has ended.

Removing completed runtime states keeps the application responsive,

predictable,

and easy to maintain.


---

# State Principles

State Management should provide a predictable and consistent runtime experience without becoming responsible for persistent business data.

Business features manage their own runtime behaviour,

while the database preserves long-term creator information.

This separation allows Aura AI to remain responsive,

maintainable,

and scalable.

---

# Runtime Independence

Each state category should manage only its own runtime responsibility.

Session State,

Feature State,

Execution State,

Connection State,

and Interface State should remain independent while sharing the same application context.

Changes within one state should not introduce unnecessary dependencies into unrelated states.

---

# Temporary by Design

Runtime state exists only while it is required.

When a task,

interaction,

or operation has completed,

its associated runtime state should be removed or reset.

Persistent information should always remain within the database rather than the application state.

---

# Predictable Behaviour

Every state should follow a consistent lifecycle.

State transitions should always be:

- Intentional.
- Observable.
- Reversible when appropriate.
- Easy to understand.

Predictable state behaviour simplifies feature development,

testing,

and long-term maintenance.

---

# Feature Isolation

Each business feature remains responsible for managing its own runtime state.

Shared platform states provide application context,

but individual features should not directly control the internal states of other features.

This separation preserves modularity while allowing features to evolve independently.

---

# Final Statement

State Management provides the runtime foundation for Aura AI.

By separating temporary runtime state from persistent business data,

Aura AI maintains a responsive,

predictable,

and scalable application architecture where every feature operates independently while sharing a consistent application context.
