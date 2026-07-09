# Onboarding

Version: 1.0
Status: Locked
Last Updated: 2026-07-09

---

# Overview

The onboarding experience introduces new users to Aura AI and prepares their account for first-time use.

Its purpose is to collect only the minimum information required for Aura AI to personalise the creator experience while allowing users to begin creating content as quickly as possible.

The onboarding flow is designed to be short, simple, and easy to complete.

---

# Objectives

The onboarding process has four primary objectives:

- Identify the creator's primary content category.
- Set the preferred language for content generation.
- Introduce the core features of Aura AI through a brief tutorial.
- Connect the creator's Threads account.

Once onboarding is completed, the user is redirected to the Home screen.

---

# Design Principles

The onboarding experience follows these principles:

### Minimal Friction

Only request information that is required for Aura AI to function.

Avoid unnecessary questions that may slow down first-time users.

---

### Learn While Setting Up

Introduce the application's core features during onboarding so users understand how Aura AI works before using it.

The tutorial should remain brief and easy to follow.

---

### Creator First

Allow creators to begin generating content as soon as onboarding is completed.

Additional preferences and account customisation can be configured later within the application.

---

# Onboarding Flow

```
Welcome

↓

Content Category

↓

Language Preference

↓

Tutorial

↓

Connect Threads Account

↓

Home
```


---

# Onboarding Flow

The onboarding process guides first-time users through a short sequence of setup screens.

Each step should require minimal effort while preparing the account for immediate use after completion.

Users cannot access the main application until onboarding has been completed.

---

## Step 1 — Welcome

The first screen welcomes the user to Aura AI.

Purpose:

- Introduce Aura AI.
- Briefly explain its purpose.
- Prepare the user for the onboarding process.

Primary Action:

- Continue

---

## Step 2 — Content Category

The user selects the primary type of content they create.

Example categories include:

- Education
- Marketing
- Sales
- Business
- Technology
- Food
- Sports
- Lifestyle
- Beauty
- Gaming
- Finance
- Entertainment
- Travel
- Productivity
- Other

This information helps personalise the creator experience throughout the application.

Primary Action:

- Continue

---

## Step 3 — Language Preference

The user selects their preferred language for content generation.

This language becomes the default language used throughout Aura AI.

Users may change this preference later within the application settings.

Primary Action:

- Continue

---

## Step 4 — Tutorial

A short walkthrough introduces the application's core features.

The tutorial briefly explains:

- Write
- Scout
- Planner
- Stats

The objective is to familiarise users with the purpose of each feature before they begin using Aura AI.

Primary Action:

- Continue

---

## Step 5 — Connect Threads Account

The user connects their Threads account.

This connection enables Aura AI to:

- Generate content for the connected account.
- Discover engagement opportunities through Scout.
- Display account performance within Stats.

The connection process should remain simple and secure.

Primary Action:

- Connect Account

Secondary Action:

- Complete Setup


---

# Tutorial

The tutorial introduces users to Aura AI's four core features.

Its purpose is to provide a basic understanding of each feature before the user begins using the application.

The tutorial should remain concise and focused.

It is intended to build familiarity rather than provide comprehensive training.

---

## Write

Write is the primary content creation workspace.

Users provide their content preferences and objectives, while Aura AI generates creator-ready Threads through its AI pipeline.

The generated content can be reviewed, edited, saved as a draft, scheduled, or published.

---

## Scout

Scout helps users discover relevant Threads conversations.

Instead of manually searching for engagement opportunities, Scout prepares context-aware reply suggestions for meaningful interactions.

Users remain in full control of reviewing, editing, regenerating, or publishing every reply.

---

## Planner

Planner organises the creator's publishing workflow.

It provides a calendar view for managing:

- Unscheduled drafts.
- Scheduled posts.
- Published posts.
- Reply history.

Planner helps creators keep their content organised in one place.

---

## Stats

Stats helps creators understand their account performance.

Charts and analytics display historical performance, while Aura AI explains meaningful trends, patterns, and content insights in simple language.

The objective is to help creators understand their analytics rather than simply display numbers.

---

# Tutorial Guidelines

The tutorial should:

- Introduce one feature at a time.
- Use clear and concise language.
- Focus on the purpose of each feature.
- Avoid overwhelming first-time users.

The tutorial is complete once all four features have been introduced.


---

# Threads Account Connection

The final onboarding step allows users to connect their Threads account to Aura AI.

A connected account enables Aura AI to provide a personalised experience across the application.

Users must successfully connect their Threads account before completing onboarding.

---

# Connection Process

The connection process follows this sequence:

```
User

↓

Connect Threads Account

↓

Threads Authentication

↓

Permission Approval

↓

Successful Connection

↓

Account Synchronisation

↓

Complete Onboarding
```

The authentication process should use the official Threads authentication flow.

Aura AI should never request the user's Threads password directly.

---

# Account Synchronisation

After a successful connection, Aura AI synchronises the information required to initialise the creator account.

Examples include:

- Threads account information.
- Public profile information.
- Account identifier.
- Initial account statistics required by the application.

Only the information necessary for Aura AI to operate should be retrieved.

---

# Connection States

The connection screen should support the following states:

### Not Connected

The user has not yet connected their Threads account.

Primary Action:

- Connect Account

---

### Connecting

Authentication is currently in progress.

The user should wait until authentication has completed.

---

### Connected

The Threads account has been successfully connected.

The user may continue to complete onboarding.

---

### Connection Failed

Authentication was unsuccessful.

The user should be informed that the connection could not be completed and be given the option to try again.

---

# Completion Requirement

Onboarding is considered complete only after:

- A content category has been selected.
- A preferred language has been selected.
- The tutorial has been completed.
- The Threads account has been successfully connected.

Once these requirements have been satisfied, the user is redirected to the Home screen.



---

# Completion

The onboarding process is completed once the user has successfully finished every required setup step.

At this point, Aura AI stores the selected onboarding preferences and prepares the application for first-time use.

The user is then redirected to the Home screen.

---

# Stored Preferences

The following information is stored after onboarding:

- Primary Content Category.
- Preferred Language.
- Tutorial Completion Status.
- Connected Threads Account.

These preferences become the initial configuration for the creator's account and may be updated later through the application settings.

---

# First-Time Experience

After onboarding, the user gains access to all core features of Aura AI.

This includes:

- Write
- Scout
- Planner
- Stats

No additional setup is required before using the application.

---

# Completion