# Draft Schema

Version: 1.0
Status: Locked
Last Updated: 2026-07-07

---

# Purpose

The Draft Schema defines the editable working state of a Thread before publication.

Its purpose is to provide creators with a flexible workspace where generated content can be reviewed, modified, saved, reopened, scheduled, or published without affecting the final published version.

Rather than representing a separate business object, the Draft Schema documents the lifecycle and behaviour of a Thread while it remains unpublished.

---

# Definition

A Draft represents an unpublished Thread that is still being actively managed by the creator.

A Draft allows creators to:

- Edit generated content.
- Save ongoing changes.
- Reopen previously saved work.
- Schedule future publication.
- Publish immediately.
- Delete unpublished work.

A Draft always belongs to a single Thread and shares the same Thread ID throughout its lifecycle.

No new Thread is created when saving or editing a Draft.

---

# Scope

The Draft Schema collaborates with multiple business schemas throughout Aura AI.

These include:

- Thread
- Planner

Draft is responsible for:

- Managing editable Thread content.
- Preserving unpublished work.
- Supporting repeated editing sessions.
- Preparing content for scheduling or publication.

Draft does not generate content.

Draft does not perform AI analysis.

Draft does not create publishing history.

Its responsibility is limited to managing the creator's unpublished editing workflow.

---

# Core Concept

Aura AI separates content creation from content publication.

```
Write
   │
   ▼
Generate Thread
   │
   ▼
Draft
   │
   ├──────────────┐
   ▼              ▼
Schedule      Publish
   │              │
   └──────┬───────┘
          ▼
      Published Thread
```

A Draft acts as the creator's working version of a Thread.

Creators may return to the same Draft multiple times, making additional edits and saving their progress before deciding to schedule or publish.

Throughout this process, the Thread maintains the same identity while the Draft manages its editable state.

This separation allows Aura AI to provide a simple editing experience without compromising the integrity of the underlying Thread object.


---

# Schema Overview

The Draft Schema represents the editable state of a Thread before publication.

Rather than creating a separate content object, Draft provides creators with a workspace for managing unpublished Threads while preserving the original Thread identity.

Every Draft always references a single Thread and shares its unique identifier throughout the entire editing lifecycle.

---

# Core Properties

Each Draft maintains the information required to support the creator's editing workflow.

Core properties include:

| Property | Description |
|----------|-------------|
| Thread ID | Unique identifier shared with the associated Thread. |
| Account Context ID | The Account Context that owns the Draft. |
| Draft Status | Current unpublished state of the Thread. |
| Current Content | Latest editable version of the Thread. |
| Last Saved At | Date and time the Draft was last saved. |
| Last Edited At | Date and time the Draft was most recently modified. |
| Scheduled Date | Planned publication date and time, if scheduled. |
| Created At | Date and time the Draft was first created. |

These properties allow Aura AI to preserve editing progress without creating duplicate business objects.

---

# Relationships

Every Draft belongs to exactly one Thread.

Relationship overview:

```
Account Context
        │
        ▼
      Thread
        │
        ▼
      Draft
        │
        ▼
     Planner
```

Relationship behaviour includes:

- Thread provides the business identity shared throughout the lifecycle.
- Draft manages the editable state of the Thread.
- Planner references the Draft while it remains unpublished and transitions to the published Thread once publication is complete.

Draft never creates a new Thread.

Instead, it continuously manages the editable version of the existing Thread until publication.


---

# Lifecycle

The Draft Schema manages the editable lifecycle of a Thread before publication.

Unlike published content, a Draft may go through multiple editing sessions while maintaining the same Thread identity.

The typical lifecycle is:

```
Generate Thread
        │
        ▼
Save Draft
        │
        ▼
Open Draft
        │
        ▼
Edit Content
        │
        ▼
Save Changes
        │
   ┌────┴────┐
   ▼         ▼
Edit Again  Schedule
   │         │
   └────┬────┘
        ▼
     Publish
```

A Draft may be opened, edited, and saved repeatedly.

Each save updates the existing Draft without creating a new Thread or a new Draft.

The Draft lifecycle ends only when the Thread is published or permanently deleted.

---

# Ownership

Every Draft belongs to exactly one Thread.

Ownership hierarchy:

```
Aura User
      │
      ▼
Account Context
      │
      ▼
     Thread
      │
      ▼
     Draft
```

The Draft inherits its ownership from the associated Thread.

At no point does the Draft become an independent business object.

It exists solely to manage the editable state of the Thread before publication.

---

# Editing Behaviour

The Draft provides creators with a persistent editing workspace.

Creators may:

- Reopen previously saved Drafts.
- Modify any part of the Thread.
- Save changes multiple times.
- Schedule publication.
- Publish immediately.
- Delete the Draft before publication.

Every saved change replaces the previous editable version.

Aura AI always preserves a single current version of the Draft.

The editing workflow remains uninterrupted until the creator decides to schedule, publish, or remove the Draft.


---

# Business Rules

The Draft Schema follows a set of rules that ensure unpublished content remains editable, consistent, and protected until publication.

## Rule 1 — Every Draft Belongs to a Thread

A Draft must always reference exactly one Thread.

Drafts never create independent content objects.

Every edit, save, schedule, or publication continues using the same Thread identity throughout the entire lifecycle.

---

## Rule 2 — Drafts Are Fully Editable

Creators may freely modify any part of a Draft before publication.

This includes:

- Thread content.
- Individual posts.
- Call-to-actions.
- Hashtags.
- Formatting.

There are no restrictions on the number of edits performed before publication.

---

## Rule 3 — Saving Updates the Existing Draft

Each save operation updates the current Draft.

Aura AI must never create duplicate Drafts when saving changes.

Only the latest saved version is preserved.

---

## Rule 4 — Publication Ends the Draft Lifecycle

Once a Draft is successfully published, it immediately stops functioning as a Draft.

The Thread continues as a published business object and becomes part of the creator's publishing history through Planner.

The Draft itself no longer appears within the Draft section.

---

## Rule 5 — Drafts Remain Independent of Publishing Decisions

Saving a Draft does not schedule publication.

Scheduling a Draft does not publish it.

Publishing always requires an explicit creator action or a previously scheduled publishing event.

This separation allows creators to prepare content without committing to immediate publication.

---

# Validation Rules

Before saving a Draft, Aura AI should validate that:

- A valid Account Context is active.
- The associated Thread exists.
- The Draft content is successfully stored.

Before scheduling or publishing a Draft, Aura AI should additionally verify that:

- The Draft contains valid content.
- The connected Threads account is available.
- Required publishing information has been provided.

If validation fails, Aura AI should preserve the latest saved Draft so the creator never loses unpublished work.

These validation rules ensure Drafts remain a reliable workspace while protecting creators from accidental data loss before publication.


---

# Business Examples

The following examples demonstrate how the Draft Schema behaves during normal creator workflows.

### Example 1 — Saving a New Draft

A creator generates a new Thread using the Write feature.

Instead of publishing immediately, the creator selects **Save Draft**.

The Thread becomes an editable Draft and appears in the Drafts section of Planner.

The creator may reopen the Draft at any time to continue working on it.

---

### Example 2 — Editing an Existing Draft

A creator reopens a previously saved Draft.

Several changes are made to the content, including revisions to multiple posts and the call-to-action.

The creator saves the Draft again.

Aura AI updates the existing Draft while preserving the same Thread identity.

No duplicate Draft or Thread is created.

---

### Example 3 — Publishing a Draft

A creator opens a saved Draft and decides to publish it.

Aura AI successfully publishes the associated Thread.

The Draft is removed from the Drafts section.

The same Thread now appears within Planner as part of the creator's published history.

The Draft lifecycle is complete.

---

# Design Rationale

The Draft Schema is designed to separate content editing from content publication.

Rather than treating Drafts as independent content objects, Aura AI models them as the editable state of a Thread before publication.

This architecture allows creators to freely edit, save, reopen, and refine their content without affecting the identity of the underlying Thread.

By maintaining a single Thread identity throughout the editing lifecycle, Aura AI avoids duplicate business objects while providing a simple and intuitive editing experience.

This approach provides:

- Flexible content editing.
- Safe preservation of unpublished work.
- Consistent business identity.
- Seamless transition from drafting to publishing.
- A clear separation between editing and publication.

---

# Final Statement

The Draft Schema represents Aura AI's editing workflow for unpublished Threads.

It provides creators with a persistent workspace where content can evolve through multiple editing sessions while maintaining a single Thread identity.

By separating editing behaviour from publication behaviour, Aura AI preserves a clean business architecture that supports flexible content creation without compromising consistency, ownership, or long-term maintainability.