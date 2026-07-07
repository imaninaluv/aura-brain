# Database Architecture

Version: 1.0
Status: Locked
Last Updated: 2026-07-07

---

# Purpose

Database Architecture defines how Aura AI organises, stores, and manages persistent business data.

Its purpose is ensuring every feature has a clear and consistent method for storing information while maintaining data ownership, integrity, and scalability.

The database supports the platform by preserving creator data across sessions without participating in system execution.

---

# Scope

Database Architecture applies to all persistent data managed by Aura AI.

Examples include:

- Creator profiles.
- Connected Threads accounts.
- Drafts.
- Scheduled posts.
- Published content.
- Analytics.
- Creator preferences.
- Knowledge Repository.

Temporary execution data, such as Execution Context and Knowledge Context, is not part of the database architecture.

These remain part of the runtime execution process.

---

# Core Principle

The database stores business data.

It does not own business data.

Every piece of persistent data belongs to one feature or one system component.

The database serves as the storage layer while ownership remains with the responsible component.

This separation preserves clear responsibilities throughout the platform.

---

# Database Philosophy

Aura AI separates ownership,

processing,

and storage into independent responsibilities.

Features create and manage their own business data.

System components manage temporary execution data.

The database provides a single, reliable location for storing persistent information without controlling feature behaviour or AI execution.

This architecture ensures the platform remains:

- Consistent.
- Scalable.
- Maintainable.
- Easy to extend.


---

# High-Level Database Architecture

Aura AI organises persistent data around business ownership rather than technical implementation.

Each feature owns its business data,

while the database provides a shared storage layer for preserving that data.

```
Aura User

↓

Connected Threads Accounts

↓

Active Account

↓

Write ─────┐

Planner ───┼──► Persistent Storage

Scout ─────┤

Stats ─────┘
```

The active Threads account determines which business data is accessed during every session.

All creator activities are isolated within their respective connected account.

---

# User Layer

The Aura User represents the platform account.

This layer manages:

- Profile.
- Subscription.
- Connected Threads accounts.
- Platform settings.

The Aura User does not directly own creator content.

Instead,

it owns the connected accounts responsible for business data.

---

# Connected Account Layer

Each connected Threads account represents an independent creator workspace.

Every connected account maintains its own:

- Drafts.
- Scheduled posts.
- Published threads.
- Published replies.
- Analytics.

Switching the active account changes the business data available throughout the platform without affecting other connected accounts.

---

# Feature Layer

Business data is created and managed by individual features.

Examples include:

Write

- Drafts.
- Published Threads.

Planner

- Scheduled Posts.

Scout

- Published Replies.

Stats

- Analytics.

Each feature remains responsible for the lifecycle of its own business data.

---

# Storage Layer

The database provides persistent storage for all business data.

It does not participate in feature logic,

AI reasoning,

or execution orchestration.

Its responsibility is preserving information so that it can be retrieved consistently across sessions.

The storage layer remains independent from business ownership,

allowing features to evolve without changing the underlying database architecture.


---

# Database Domains

Aura AI organises persistent data into independent business domains.

Each domain represents one area of responsibility within the platform.

Domains remain independent while sharing a common storage architecture.

---

# Platform Domain

The Platform Domain stores information related to the Aura platform itself.

Examples include:

- Aura User.
- Connected Threads Accounts.
- Subscription.
- Creator Preferences.

The Aura User owns one or more connected Threads accounts.

One connected account becomes the Active Account during each session.

---

# Write Domain

The Write Domain manages original creator content.

Examples include:

- Drafts.
- Published Threads.

Published Threads store a lightweight historical record for creator reference.

The database preserves the first post of each published thread together with its associated publishing information.

The complete thread chain is not stored as part of the historical archive.

---

# Planner Domain

The Planner Domain manages future publishing activities.

Examples include:

- Scheduled Posts.

Planner does not own published content.

Instead,

it references Published Threads and Published Replies when constructing the creator activity timeline.

---

# Scout Domain

The Scout Domain manages creator engagement activities.

Persistent business data includes:

- Published Replies.

Temporary AI-generated reply suggestions are not stored within the database.

Only replies successfully published by the creator become part of the persistent history.

---

# Stats Domain

The Stats Domain stores analytical information generated from creator activities.

Examples include:

- Performance Analytics.
- Growth Metrics.
- Historical Insights.

Stats consumes published content from other domains without becoming its owner.

---

# Domain Independence

Each database domain owns only its own business data.

Domains may reference data owned by other domains,

but ownership always remains unchanged.

This separation allows every feature to evolve independently while preserving a consistent and maintainable database architecture.


---

# Database Relationships

Database domains remain independent while collaborating through clearly defined relationships.

Each domain owns its own business data,

but may reference data owned by another domain when required.

Ownership is never transferred between domains.

---

# Platform Relationships

The Aura User represents the platform account.

Each Aura User may connect one or more Threads accounts.

One connected account becomes the Active Account during each session.

All creator business data belongs to the connected Threads account rather than the Aura User itself.

---

# Feature Relationships

Business domains operate independently while sharing creator context.

Examples include:

- Write creates published threads.
- Planner references scheduled posts and published content.
- Scout creates published replies.
- Stats analyses published creator activities.

Each feature accesses only the information required to perform its responsibility.

---

# Cross-Domain References

Some business data is shared across multiple features.

Examples include:

- Planner displaying published threads created by Write.
- Planner displaying published replies created by Scout.
- Stats analysing content created by Write and Scout.

Shared access does not change ownership.

The original feature always remains responsible for its own business data.

---

# Relationship Principles

Database relationships should always remain:

- Ownership-driven.
- Feature-oriented.
- Independent.
- Predictable.

Features should collaborate through shared references while maintaining clear ownership boundaries.

This architecture allows new features to integrate with existing domains without restructuring previously established relationships.

---

# Database Principles

The Aura AI database should provide a reliable foundation for storing creator business data.

It should remain independent from feature logic,

AI execution,

and system orchestration.

Its responsibility is preserving persistent information while allowing features to manage their own business processes.

---

# Single Source of Truth

Every piece of business data should exist in one authoritative location.

Features should reference existing data rather than creating duplicate copies.

This ensures consistency across Write,

Planner,

Scout,

and Stats.

---

# Business Ownership

Every persistent data object should have one clearly defined owner.

Features remain responsible for:

- Creating data.
- Updating data.
- Maintaining data.
- Removing data when required.

The database stores business data without becoming its owner.

---

# Data Consistency

All connected Threads accounts should remain isolated from one another.

Switching the Active Account should immediately change the available business data without affecting data owned by other connected accounts.

Creator activities,

analytics,

drafts,

and schedules should always remain associated with their originating connected account.

---

# Future Scalability

The database architecture should support future platform growth without requiring fundamental structural changes.

New features should introduce their own business domains while respecting existing ownership,

relationships,

and storage principles.

This allows Aura AI to evolve while maintaining a stable and maintainable database architecture.

---

# Final Statement

The Database Architecture provides a consistent method for organising,

storing,

and preserving creator business data.

By separating business ownership from persistent storage,

Aura AI maintains a scalable,

feature-oriented,

and technology-independent database architecture capable of supporting multiple connected creator accounts and future platform expansion.
