# Aura AI System Architecture

Version: 1.0  
Status: Locked  
Last Updated: 2026-07-05

---

# Purpose

This document defines the complete system architecture behind Aura AI.

It explains how every content request flows through the system, how the internal AI engines operate, and how Aura Brain controls the behaviour of the application.

This document is intended for developers and AI engineers only.

---

# Architecture Philosophy

Aura AI is designed around one core principle:

> Users should experience a simple interface while the AI handles the complexity internally.

Everything related to content quality, validation, optimisation, and decision making happens behind the scenes.

The user should never need to understand how the system works internally.

---

# High-Level Architecture

Aura AI follows the architecture below.

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

---

# Component Overview

## 1. Aura AI Frontend

The frontend is responsible for user interaction only.

Responsibilities include:

- Collect user inputs
- Send generation requests
- Display generated threads
- Manage drafts
- Manage scheduling
- Connect social media accounts
- Display analytics

The frontend never performs content generation or validation.

---

## 2. Gemini API

Gemini is the language model responsible for generating and refining content.

Gemini does not make independent decisions.

Its behaviour is controlled entirely by Aura Brain.

---

## 3. Aura Brain

Aura Brain is the central knowledge base powering Aura AI.

It contains:

- Product rules
- Writing rules
- HERO Engine rules
- AURA Engine rules
- Writing mode behaviour
- Scoring rules
- UX behaviour
- Prompt templates
- Internal examples

Aura Brain acts as the single source of truth for every AI interaction.

If Aura Brain changes, the AI behaviour changes.

The application itself should never contain hardcoded writing logic.

---

# HERO Engine

HERO is the internal content generation engine.

It is never exposed to users.

Its responsibility is to generate the initial version of the requested content based on:

- Writing Mode
- Topic
- Language
- Hook Style
- Thread Count
- Posts Per Thread
- Aura Brain rules

HERO focuses only on generating content.

It does not validate quality.

---

# AURA Engine

AURA is the internal validation engine.

It is never exposed to users.

Its responsibility is to review HERO's output before anything is shown to the user.

AURA does not generate new threads.

Instead, it improves individual sections that do not meet Aura Brain standards.

---

# Internal Generation Flow

Whenever a user presses Generate, the following process happens internally.

User Request

↓

Load Aura Brain

↓

Run HERO Engine

↓

Run AURA Engine

↓

Return Approved Output

↓

Display Results

This entire workflow happens within a single AI generation pipeline.

The user never sees the internal processing.

---

# HERO Generation Flow

HERO performs the following tasks:

Receive user request

↓

Read Writing Mode

↓

Read Topic

↓

Read User Settings

↓

Generate thread using Aura Brain rules

↓

Pass output to AURA

HERO never evaluates its own output.

---

# AURA Validation Flow

AURA performs four internal stages.

Analyze

↓

Understand

↓

Review

↓

Approve

Each stage has a specific responsibility.

---

## Analyze

Analyze scans the generated thread.

It checks:

- Writing Mode
- HERO structure
- Topic consistency
- Content flow
- Thread structure
- Human readability

No content is modified during this stage.

---

## Understand

Understand identifies weak sections inside the generated thread.

Examples include:

- Weak Hook
- Weak Engage
- Weak Reveal
- Weak Outcome
- Wrong writing mode behaviour
- Wrong bait
- Generic AI wording

If a section does not meet Aura Brain standards, only that specific section is regenerated.

The entire thread is never regenerated unless explicitly requested by the user.

Internal reasoning generated during this stage is never shown to users.

---

## Review

Review evaluates the improved thread.

It verifies that:

- HERO methodology is followed
- Writing Mode objective is achieved
- Thread quality meets Aura Brain standards

Review generates an internal compliance score.

This score is used only for system validation.

---

## Approve

Once validation is complete, AURA approves the final thread.

Only approved threads are returned to users.

Users never see rejected versions.

---

# Writing Mode Validation

AURA validates every thread according to the selected Writing Mode.

Selling Mode

Goal:

Sell the solution.

Never sell the product.

Outcome:

Readers should imagine a better outcome after using the solution.

---

Informative Mode

Goal:

Help readers gain a new perspective.

Outcome:

Readers should feel smarter after reading and naturally continue the discussion.

---

Engagement Mode

Goal:

Create opinions and conversations.

Outcome:

Readers should feel encouraged to leave comments and participate.

---

# External Aura Score

After approval, every generated thread receives an overall Aura Score.

The score is shown to users only as a prioritisation indicator.

Purpose:

Help users identify which generated thread should be prioritised for publishing.

Aura Score does NOT predict virality.

Aura Score only measures compliance with Aura Brain standards.

---

# User Editing

Once the approved thread reaches the user, Aura AI's responsibility is complete.

If the user edits the content:

Approved Thread

↓

User Edit

↓

Draft Mode

From this point onward:

- HERO no longer modifies the content.
- AURA no longer validates the content.
- The edited version belongs entirely to the user.

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

Schedule Draft opens the scheduling interface where users choose a future date and time.

Post Now immediately publishes the approved content.

---

# System Boundaries

Aura AI is responsible for:

- Generating content
- Validating quality
- Improving weak sections
- Delivering approved output

Aura AI is NOT responsible for:

- Predicting virality
- Forcing users to follow recommendations
- Editing user-modified drafts
- Making publishing decisions

The creator always has the final decision.

---

# Architecture Principle

Aura AI is intentionally designed to hide internal complexity.

Users interact with one product.

Internally, multiple AI engines work together to deliver the final experience.

The user should never need to know that HERO and AURA exist.

To the user, there is only one assistant:

Aura AI.
