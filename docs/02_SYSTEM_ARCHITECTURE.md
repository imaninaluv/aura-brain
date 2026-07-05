# Aura AI System Architecture

Version: 1.0  
Status: Locked  
Last Updated: 2026-07-05

---

# Purpose

This document defines the complete technical architecture behind Aura AI.

It explains how user requests flow through the system, how the internal AI engines operate, and how Aura Brain controls every AI decision.

This documentation is intended for developers and AI engineers only.

---

# Architecture Philosophy

Aura AI is designed around one core principle:

> **The user experiences simplicity while the AI handles complexity.**

Users should never need to understand how content is generated internally.

Every strategic decision, writing decision, validation process, optimisation, and quality control happens entirely behind the scenes.

To users, there is only one product:

Aura AI.

---

# High-Level Architecture

```
User

↓

Aura AI Frontend

↓

Gemini API (Google AI Studio)

↓

Aura Brain

↓

HERO Engine

↓

AURA Engine

↓

Approved Output

↓

Aura AI Frontend

↓

User
```

---

# Component Overview

## Aura AI Frontend

The frontend is responsible only for user interaction.

Responsibilities include:

- Collect user inputs
- Connect social media accounts
- Display generated threads
- Manage drafts
- Manage scheduling
- Display analytics
- Handle publishing actions

The frontend never generates or validates content.

---

## Gemini API

Gemini is the language model powering Aura AI.

Gemini is responsible for language generation only.

It does not decide how to write.

Every writing behaviour is controlled by Aura Brain.

---

## Aura Brain

Aura Brain is the central knowledge base of Aura AI.

It stores every rule that controls the AI.

Contents include:

- Product philosophy
- Writing methodologies
- HERO Engine behaviour
- AURA Engine behaviour
- Writing mode definitions
- Human writing guidelines
- Psychology rules
- CTA rules
- Scoring standards
- Prompt templates
- Internal examples

Aura Brain is the single source of truth.

The application should never contain hardcoded writing logic.

If Aura Brain changes, the AI behaviour changes.

---

## HERO Engine

HERO is the internal content generation engine.

Its responsibility is to transform user intent into structured, high-retention Threads.

HERO does not validate quality.

HERO only generates content.

---

## AURA Engine

AURA is the internal validation engine.

Its responsibility is to review HERO's output before it reaches the user.

AURA improves weak sections, validates writing quality, and ensures every generated thread follows Aura Brain standards.

Only approved content is returned to users.

---

# User Input

Before generation begins, Aura AI collects the following information:

Required

- Writing Mode
- Topic
- Connected Account
- Number of Threads

Optional

- Language
- Tone
- Promotion Link
- Link in Bio

These inputs become the generation context used by HERO.

---

# Generation Pipeline

Every time the user presses **Generate**, Aura AI follows a single generation pipeline.

```
Load Aura Brain

↓

Read User Inputs

↓

Run HERO Engine

↓

Run AURA Engine

↓

Return Approved Output

↓

Display Results
```

The user never sees this process.

---

# HERO Generation Process

HERO follows four internal stages.

```
Understand

↓

Plan

↓

Structure

↓

Generate
```

---

## Understand

HERO identifies:

- Writing Mode
- User objective
- Topic
- Tone
- Language
- Promotion settings

HERO determines the intended outcome before writing begins.

---

## Plan

HERO decides the overall writing strategy.

Examples include:

- Thread direction
- Psychological flow
- Reading progression
- Curiosity placement
- Reveal timing
- Outcome strategy

Planning always happens before writing.

---

## Structure

HERO determines the most appropriate thread structure.

Possible outputs include:

```
H

↓

E

↓

R

↓

O
```

or

```
H

↓

E

↓

R1

↓

R2

↓

O
```

The structure depends entirely on the topic.

Users never manually choose the structure.

---

## Generate

Once planning is complete, HERO writes the thread.

If multiple threads are requested, HERO generates different angles while maintaining the selected Writing Mode.

Example:

Thread 1

Educational Angle

Thread 2

Contrarian Angle

Thread 3

Story Angle

Every thread must pursue the same objective while providing different perspectives.

---

# AURA Validation Process

After HERO finishes writing, AURA immediately begins validation.

AURA follows four internal stages.

```
Analyze

↓

Understand

↓

Review

↓

Approve
```

---

## Analyze

Analyze scans the generated thread.

Checks include:

- Writing Mode
- Topic consistency
- HERO structure
- Thread flow
- Human readability
- Overall coherence

No modifications happen during this stage.

---

## Understand

Understand identifies sections that fail Aura Brain standards.

Possible issues include:

- Weak Hook
- Weak Engage
- Weak Reveal
- Weak Outcome
- Wrong writing mode behaviour
- Generic AI wording
- Weak curiosity
- Weak emotional progression

If necessary, AURA regenerates only the weak section.

The entire thread is never regenerated.

Internal reasoning produced during this stage is never shown to users.

---

## Review

Review verifies that:

- HERO methodology is followed
- Writing Mode objective is achieved
- The thread meets Aura Brain standards

An internal compliance score is generated.

This score is used only by Aura AI.

---

## Approve

Once validation is complete, AURA approves the thread.

Only approved content is displayed to the user.

Rejected versions are never exposed.

---

# Promotion Behaviour

Promotion is optional.

If no Promotion Link is provided:

HERO generates a normal thread without promotional content.

---

If a Promotion Link is provided:

HERO naturally integrates promotion into the Outcome section.

Promotion should always feel helpful, conversational, and value-driven.

Direct selling is never allowed.

---

If **Link in Bio** is enabled:

HERO naturally references the user's bio as part of the CTA.

Example:

"I left more details in my bio if you're curious."

---

If both **Promotion Link** and **Link in Bio** are provided:

HERO combines both naturally.

Example:

"I explained everything in my bio, but if you want to skip straight to it, here's the link."

The CTA should always prioritise curiosity before action.

Readers should feel motivated to explore the solution themselves instead of feeling pressured to buy.

---

# Writing Mode Objectives

Every generated thread must satisfy the selected Writing Mode.

---

## Selling Mode

Goal

Sell the solution.

Never sell the product.

Outcome

Readers should imagine a better life after using the solution.

---

## Informative Mode

Goal

Help readers gain a new perspective.

Outcome

Readers should feel smarter after reading while naturally continuing the discussion.

---

## Engagement Mode

Goal

Create opinions.

Outcome

Readers should feel encouraged to leave comments and participate in the conversation.

---

# External Aura Score

After approval, every generated thread receives an overall Aura Score.

The score exists for one purpose:

Help users decide which generated thread should be prioritised for publishing.

Aura Score does not predict virality.

Aura Score measures compliance with Aura Brain standards.

---

# User Editing

Once approved content reaches the user:

HERO's responsibility ends.

AURA's responsibility ends.

If the user edits the thread:

```
Approved Thread

↓

User Edit

↓

Draft Mode
```

From this point onward, the content belongs entirely to the user.

Aura AI no longer validates or modifies the edited version.

---

# Publishing Workflow

Approved Thread

↓

User Decision

↓

Copy

OR

Save Draft

OR

Schedule Draft

OR

Post Now

Save Draft stores the content without publishing.

Schedule Draft opens the scheduling interface where users select a future date and time.

Post Now immediately publishes the approved content.

---

# System Boundaries

Aura AI is responsible for:

- Planning
- Generating
- Validating
- Improving
- Delivering approved content

Aura AI is NOT responsible for:

- Predicting virality
- Editing user-modified drafts
- Making publishing decisions
- Forcing users to follow AI recommendations

The creator always has the final decision.

---

# Architecture Principle

Aura AI is intentionally built using multiple internal AI components while exposing only one experience to users.

Users never interact with:

- Aura Brain
- HERO Engine
- AURA Engine

Users interact only with Aura AI.

Everything else happens behind the scenes.
