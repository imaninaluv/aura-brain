# Planner Schema

Version: 1.0
Status: Locked
Last Updated: 2026-07-07

---

# Purpose

The Planner Schema defines the scheduling, publishing timeline, and activity history within Aura AI.

Its purpose is to provide creators with a unified view of their content lifecycle, from unscheduled drafts to scheduled publications and historical publishing records.

Rather than acting as a content owner, the Planner organises and visualises business objects created throughout Aura AI.

---

# Definition

A Planner is the creator's publishing timeline.

It provides a structured view of content based on its current publishing state.

The Planner consists of two primary areas:

- Drafts
- Calendar

Drafts contain Threads that have been saved but not yet scheduled.

The Calendar displays scheduled and published activities organised by date.

The Planner itself does not store creator content.

Instead, it references existing business objects and presents them in a timeline designed for planning and reviewing publishing activity.

---

# Scope

The Planner Schema collaborates with multiple business schemas throughout Aura AI.

These include:

- Thread
- Reply
- Stats

Planner is responsible for:

- Displaying unscheduled Drafts.
- Displaying scheduled Threads.
- Recording published Thread history.
- Recording published Reply history.

Planner does not generate content.

Planner does not perform AI analysis.

Planner does not manage creator preferences.

Its responsibility is limited to organising publishing activities in a simple and predictable timeline.

---

# Core Concept

Aura AI separates unpublished work from scheduled and published activities.

```
Planner

├── Drafts
│      │
│      └── Unscheduled Threads
│
└── Calendar
       │
       ├── Scheduled Threads
       └── Published Activity
              ├── Threads
              └── Replies
```

Drafts remain outside the calendar until the creator schedules or publishes them.

Once scheduled, the corresponding Thread appears on its selected publication date.

After successful publication, the same Planner entry becomes part of the creator's permanent publishing history.

This approach allows creators to manage future content while maintaining a complete chronological record of everything they have published.


---

# Schema Overview

The Planner Schema provides a structured view of the creator's publishing activities.

Rather than storing content itself, the Planner references existing business objects and organises them according to their publishing state.

Every item displayed within the Planner originates from another business schema.

Planner simply determines where and when each item should appear.

---

# Core Properties

Each Planner item contains the minimum information required to organise creator activities.

Core properties include:

| Property | Description |
|----------|-------------|
| Planner Item ID | Unique identifier for the Planner entry. |
| Account Context ID | The Account Context that owns the activity. |
| Source Type | Indicates whether the item references a Thread or Reply. |
| Source ID | Identifier of the referenced business object. |
| Planner Status | Current planner state (Draft, Scheduled, Published). |
| Scheduled Date | Planned publishing date and time, if scheduled. |
| Published Date | Actual publishing date and time after successful publication. |
| Created At | Date and time the Planner entry was first created. |
| Last Updated | Date and time the Planner entry was last modified. |

These properties allow Planner to organise activities without duplicating business data.

---

# Relationships

Every Planner item belongs to exactly one Account Context.

Relationship overview:

```
Account Context
        │
        ▼
     Planner
        │
   ┌────┴──────────┐
   ▼               ▼
Thread          Reply
        │
        ▼
      Stats
```

Planner references existing business objects rather than owning them.

Relationship behaviour includes:

- Drafts reference existing Thread objects.
- Scheduled entries reference existing Thread objects.
- Published Thread history references the same Thread after publication.
- Published Reply history references the corresponding Reply object.

Planner never creates duplicate Threads or Replies.

Instead, it maintains a chronological view of creator activities using existing business objects as the single source of truth.


---

# Lifecycle

The Planner organises creator activities according to their publishing lifecycle.

Unlike business objects such as Threads or Replies, the Planner does not create or own content.

Instead, it reflects the current state of existing business objects.

The typical lifecycle for a Thread within Planner is:

```
Generate Thread
        │
        ▼
Save Draft
        │
   ┌────┴────┐
   ▼         ▼
Publish   Schedule
Immediately    │
               ▼
          Published
```

Replies follow a simpler lifecycle:

```
Publish Reply
      │
      ▼
Published
```

Once published, both Threads and Replies become permanent historical records within the Planner.

---

# Ownership

The Planner does not own business content.

Instead, it references existing business objects and organises them into a publishing timeline.

Ownership hierarchy:

```
Aura User
      │
      ▼
Account Context
      │
      ├──────────────┐
      ▼              ▼
   Thread         Reply
      │              │
      └──────┬───────┘
             ▼
          Planner
```

Planner never duplicates content.

Every Planner entry always references its original business object.

---

# Planner Behaviour

The Planner maintains two distinct areas of responsibility.

## Drafts

The Draft section contains Threads that have been saved but not yet scheduled or published.

Drafts remain editable and are intentionally separated from the calendar to simplify content management.

Once a Draft is scheduled or published, it is removed from the Draft section.

---

## Calendar

The Calendar displays activities based on their publication timeline.

It includes:

- Scheduled Threads.
- Published Threads.
- Published Replies.

When a scheduled Thread is successfully published, the existing calendar entry updates its status from **Scheduled** to **Published**.

The Planner preserves all published activities indefinitely, allowing creators to review their complete publishing history over time.

---

# Business Rules

The Planner Schema follows a set of rules that ensure creator activities remain organised, predictable, and historically accurate.

## Rule 1 — Planner Does Not Own Content

Planner never creates or owns business content.

All Planner entries must reference existing Thread or Reply objects.

Planner is responsible only for organising and presenting those objects within the appropriate publishing view.

---

## Rule 2 — Drafts Remain Outside the Calendar

Threads saved as Drafts should appear only within the Draft section.

Drafts must not appear on the calendar until the creator schedules them.

This separation allows creators to manage unpublished work without cluttering the publishing timeline.

---

## Rule 3 — Scheduled Items Transition to Published

When a scheduled Thread is successfully published, the existing Planner entry updates its status from **Scheduled** to **Published**.

Planner should never create duplicate entries during this transition.

The publishing timeline must continue referencing the same Thread throughout its lifecycle.

---

## Rule 4 — Published History Is Permanent

Published Threads and published Replies become permanent historical records.

Planner should preserve publishing history indefinitely unless explicitly removed by the creator.

Historical activities provide the chronological foundation for future reporting, statistics, and publishing reviews.

---

## Rule 5 — Planner Reflects Business Objects

Planner should always reflect the current state of its referenced business objects.

Changes to a Thread or Reply should automatically be represented within Planner whenever applicable.

Planner must never maintain independent versions of business data.

Instead, it always references the original business object as the single source of truth.

---

# Validation Rules

Before displaying Planner data, Aura AI should validate that:

- A valid Account Context is active.
- Every Planner entry references an existing business object.
- Scheduled publication dates remain valid.
- Published records correspond to successfully completed publishing operations.

Before moving an item between Planner views, Aura AI should additionally verify that:

- The underlying Thread or Reply has changed state appropriately.
- No duplicate Planner entries will be created.

If validation fails, Planner should preserve the most recent valid state until the issue has been resolved.

These validation rules ensure the publishing timeline remains accurate, reliable, and fully synchronised with the creator's business objects.

---

# Business Examples

The following examples demonstrate how the Planner Schema behaves during normal creator workflows.

### Example 1 — Saving a Draft

A creator generates a new Thread but decides not to publish it immediately.

The creator selects **Save Draft**.

The Thread appears in the **Drafts** section of Planner.

The calendar remains unchanged because no publication date has been assigned.

The creator may return to the Draft at any time to continue editing, schedule it, or publish it immediately.

---

### Example 2 — Scheduling a Thread

A creator schedules a Thread for publication on **15 July at 9:00 AM**.

The Thread is removed from the Drafts section.

A new entry appears on the Planner calendar for **15 July** with a **Scheduled** status.

When the scheduled publication completes successfully, the same calendar entry updates its status to **Published**.

No duplicate Planner entry is created.

---

### Example 3 — Reviewing Publishing History

A creator opens the Planner and selects a previous date.

The selected date displays all publishing activities that occurred on that day.

Activities may include:

- Published Threads.
- Published Replies.

The Planner presents these activities as chronological history, allowing the creator to review past publishing activity without distinguishing between different content types in the calendar view.

---

# Design Rationale

The Planner Schema is designed to provide a clear separation between content creation and content organisation.

Aura AI treats Threads and Replies as business objects, while the Planner serves as the publishing timeline that references those objects.

By separating Drafts from the calendar, creators can manage unfinished work without cluttering their publishing schedule.

Once content is scheduled or published, the Planner automatically reflects its lifecycle while continuing to reference the original business object.

This architecture provides:

- A cleaner planning experience.
- A complete publishing history.
- Consistent business ownership.
- A single source of truth for creator content.

---

# Final Statement

The Planner Schema represents Aura AI's publishing timeline.

It organises drafts, scheduled content, and historical publishing activities into a single, predictable workspace without duplicating business data.

By continuously reflecting the state of existing Threads and Replies, the Planner provides creators with a reliable overview of both upcoming publications and past activity while preserving the platform's single source of truth architecture.
