# Account Context Schema

Version: 1.0
Status: Locked
Last Updated: 2026-07-07

---

# Purpose

Account Context defines the active working environment for Aura AI.

It represents the currently selected Threads account and provides the shared context used across every business feature.

Unlike the User Profile, which stores creator preferences, Account Context determines which connected Threads account the platform is currently operating on.

Every feature should read from the active Account Context before performing any business operation.

---

# Schema Overview

An Account Context represents one connected Threads account within a single Aura AI account.

Each Aura AI account may contain multiple connected Threads accounts.

Only one Account Context can be active at any given time.

Switching the active account updates the context used by:

- Home
- Write
- Scout
- Planner
- Stats

without affecting the creator's overall Aura AI account.

---

# Core Properties

Each Account Context contains:

- Connected Threads Account
- Threads Username
- Account Status
- Active Context State
- Connected Timestamp
- Last Active Timestamp

The schema represents the current operating context rather than permanent creator information.

---

# Relationships

Account Context collaborates with the following business schemas:

- User Profile
- Thread
- Scout
- Planner
- Stats
- Draft
- Reply
- Analysis

Every business object belongs to exactly one active Account Context.

This separation ensures that activity from different Threads accounts never becomes mixed together.

---

# Context Switching

When creators switch between connected Threads accounts:

- Home updates to the selected account.
- Write generates content for the selected account.
- Scout searches using the selected account.
- Planner displays activities belonging to the selected account.
- Stats display analytics for the selected account.
- Drafts belonging to the selected account become available.

The switch changes the active working context only.

No creator preferences or historical data are lost.

---

# Ownership

Each Account Context owns:

- Thread history
- Reply history
- Drafts
- Planner activities
- Statistics
- AI analysis history

These business objects remain isolated within their respective account contexts.

---

# Final Statement

Account Context establishes the operational boundary for every creator workflow within Aura AI.

By separating multiple connected Threads accounts into independent contexts, the platform allows creators to manage several brands or identities from a single Aura AI account while preserving complete separation between their content, engagement history, planning, and performance.
