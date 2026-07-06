# Planner Feature

Version: 2.0
Status: Locked
Last Updated: 2026-07-06

---

# Identity

Planner is Aura AI's content scheduling feature.

Its responsibility is helping creators organise and manage their publishing schedule through a visual content calendar.

Planner does not generate content.

Planner does not analyse performance.

Planner manages scheduled publishing activities.

---

# Purpose

The Planner feature provides creators with a central place to organise upcoming content.

Its objective is making content planning simple, clear, and easy to manage.

The calendar should present information without increasing creator workload.

---

# Inputs

Planner receives creator actions.

Possible inputs include:

- Create schedule.
- Update schedule.
- Remove schedule.
- View calendar.

Every planner action begins with creator interaction.

---

# Outputs

Planner returns updated calendar information.

Possible outputs include:

- Updated schedule.
- Calendar view.
- Scheduled content.
- Scheduling status.

Planner should always present the latest calendar state.

---

# Core Principle

Planner should help creators stay organised without making planning more complicated.

The calendar should remain visual, simple, and easy to understand.

Creators manage the schedule.

Aura AI supports the workflow when requested.

---

# Feature Flow

Every planner action follows the same workflow.

```
Creator Action

↓

Planner

↓

Update Calendar

↓

Display Result
```

AI generation occurs only when explicitly requested by the creator.

Planner should never generate content automatically.



---

# Planner Workflow

Every planner interaction begins with loading the creator's calendar.

```
Creator

↓

Open Planner

↓

Load Calendar

↓

Display Schedule
```

Planner should always display the creator's latest scheduling information.

---

# Calendar Loading

When the Planner is opened,

the feature should retrieve:

- Scheduled posts.
- Saved drafts.
- Calendar view preference.

The creator should immediately see their current planning status.

---

# Creator Interaction

The creator interacts directly with the calendar.

Possible interactions include:

- Change calendar view.
- Select a scheduled post.
- Open saved drafts.

Planner should respond immediately without performing unnecessary AI reasoning.

---

# Content Navigation

When the creator selects existing content,

Planner determines the appropriate destination.

```
Scheduled Post

↓

Planner

↓

Write Feature
```

```
Draft

↓

Planner

↓

Write Feature
```

Planner should never modify content directly.

Content editing always belongs to the Write feature.

---

# Calendar Updates

Whenever content is created, updated, scheduled, published, or deleted,

Planner should refresh the calendar automatically.

The displayed schedule should always reflect the latest available information.

---

# Workflow Principles

Planner is responsible for managing the creator's schedule,

not managing content.

The calendar should remain the central place for viewing publishing activities,

while content creation and editing remain within the Write feature.



---

# Calendar Views

Planner provides multiple calendar views to help creators manage their publishing schedule.

Available views include:

- Daily View
- Weekly View
- Monthly View

Each view displays the same scheduling data using a different layout.

Changing the calendar view should never modify scheduled content.

---

# Scheduled Posts

Scheduled posts appear directly on the calendar.

Selecting a scheduled post opens available actions.

Available actions include:

- Edit
- Post Now
- Delete

Planner should never edit scheduled content directly.

Selecting **Edit** or **Post Now** transfers the creator to the Write feature.

Deleting a scheduled post removes it from the calendar immediately.

---

# Draft Tray

Planner provides quick access to saved drafts through the Draft Tray.

The Draft Tray appears above the calendar for easy access.

Selecting a draft opens available actions.

Available actions include:

- Edit
- Post Now
- Delete

Planner should never edit draft content directly.

Selecting **Edit** or **Post Now** transfers the creator to the Write feature.

Deleting a draft removes it from the Draft Tray.

---

# Navigation Rules

Planner is responsible for schedule management.

Write is responsible for content management.

Whenever content requires editing or publishing,

Planner should redirect the creator to the Write feature.

Planner should never duplicate editing functionality.

---

# Behaviour Principles

Planner should remain simple, visual, and lightweight.

Its primary responsibility is helping creators view and organise scheduled content.

Content creation and editing always belong to the Write feature.

Planner should provide visibility,

not additional complexity.



---

# Feature Integration

Planner works together with other Aura AI features.

Its responsibility is connecting scheduling with content management while keeping each feature independent.

Planner should never duplicate the responsibilities of another feature.

---

# Write Integration

Whenever a creator chooses to edit or publish content,

Planner transfers the request to the Write feature.

Examples include:

- Edit Scheduled Post
- Post Now
- Edit Draft
- Post Draft Now

Content editing always takes place in the Write feature.

---

# Calendar Synchronisation

Planner should always reflect the latest content status.

Changes made through the Write feature should automatically update the calendar.

Examples include:

- New scheduled post.
- Updated scheduled post.
- Deleted scheduled post.
- Published post.

The calendar should always remain synchronised with the latest creator activity.

---

# Navigation Behaviour

Planner serves as the creator's scheduling hub.

It should allow creators to move naturally between:

- Calendar
- Drafts
- Write

Navigation should feel seamless.

Creators should never need to manually refresh the planner after completing an action.

---

# Integration Principles

Each Aura AI feature should maintain a single responsibility.

Planner manages schedules.

Write manages content.

AI components manage reasoning and validation.

Features should work together without overlapping responsibilities.



---

# Failure Rules

Planner should stop the current action whenever required scheduling information is unavailable.

Examples include:

- Calendar data unavailable.
- Scheduled content not found.
- Draft not found.
- Invalid planner request.

Planner should never display outdated or incomplete scheduling information.

---

# Retry Rules

Retry should occur only when the failure is temporary.

Examples include:

- Temporary loading interruption.
- Temporary synchronisation failure.
- Temporary processing issue.

Retry should never occur when creator action is required.

If additional creator input is needed,

the current action should stop until the creator completes the request.

---

# Design Principles

Planner should always:

- Keep scheduling simple.
- Present information clearly.
- Minimise creator effort.
- Maintain an organised publishing calendar.

Creators should always understand their publishing schedule at a glance.

---

# Engine Principle

Planner is Aura AI's scheduling workflow.

It does not generate content.

It does not perform AI reasoning.

It does not validate outputs.

Its responsibility is helping creators organise scheduled posts and drafts while providing seamless navigation to the Write feature whenever content management is required.

---

# Final Statement

Planner exists to give creators a clear and organised view of their publishing schedule.

Its purpose is not deciding when creators should publish,

but making it easy for creators to manage their own publishing plan.

The calendar should remain simple, visual, and reliable.

Content belongs to the Write feature.

Scheduling belongs to Planner.