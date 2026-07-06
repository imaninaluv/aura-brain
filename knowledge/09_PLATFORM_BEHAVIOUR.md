# Platform Behaviour

Version: 1.0
Status: Locked
Last Updated: 2026-07-05

---

# Purpose

This document defines how Aura AI should understand, adapt to, and learn from the active Threads account.

Aura AI does not simply generate content.

It continuously observes account behaviour, learns from performance, and adapts its recommendations while keeping each Threads account completely independent.

Every Active Account should behave as though it has its own dedicated Aura AI.

---

# Core Philosophy

Every creator account is different.

Different audiences.

Different goals.

Different writing styles.

Different content.

Different performance.

Aura AI should never assume that one account behaves like another.

Instead,

Aura AI should fully adapt to whichever Threads account is currently active.

---

# Active Account

Aura AI always operates using one Active Account.

Version 1 supports:

- Multiple Threads accounts

Only one account may be active at any given time.

When the Active Account changes,

Aura AI should immediately switch its entire working context.

The selected account becomes the only source of truth until another account is activated.

---

# Account Context

Each Threads account maintains its own independent AI context.

Account Context includes:

- Writing history.
- Topic history.
- Scout history.
- Performance history.
- AI learning history.
- Drafts.
- Scheduled posts.
- Preferred Writing Mode.
- Preferred tone.
- Frequently generated topics.
- Best-performing content.

Aura AI should continuously build knowledge for each account separately.

---

# Context Isolation

Context must never be shared across different Threads accounts.

Learning from one account should never influence another account.

Examples:

A business account should not receive recommendations based on a personal account.

A personal account should not receive Scout opportunities based on an affiliate account.

Every account should feel completely independent.

Switching accounts should feel like switching to another dedicated AI assistant.

---

# Context Switching

Whenever the user changes the Active Account,

Aura AI should immediately:

Unload the current context.

↓

Load the selected account context.

↓

Refresh Home.

↓

Refresh Scout.

↓

Refresh Write.

↓

Refresh Planner.

↓

Refresh Stats.

↓

Resume using the selected account only.

The transition should feel immediate and seamless.

---

# Home Behaviour

Home should always summarise the currently active account.

This includes:

- Today's Mission.
- Weekly Streak.
- Yesterday's Performance.
- Top Performing Posts.

Changing the Active Account should immediately refresh every Home metric.

---

# Write Behaviour

Write should automatically adapt to the active account.

Aura AI should understand:

- Frequently discussed topics.
- Preferred Writing Mode.
- Preferred tone.
- Previous writing behaviour.
- Historical content patterns.

Previous behaviour should improve future generation without requiring users to repeatedly configure the same preferences.

---

# Scout Behaviour

Scout should discover conversations relevant to the active account only.

Scout recommendations should prioritise:

- The account's primary niche.
- Frequently generated topics.
- High-performing historical topics.
- Relevant trending discussions.

Scout should never recommend discussions based on another account's learning history.

---

# Planner Behaviour

Planner belongs exclusively to the active account.

This includes:

- Drafts.
- Scheduled posts.
- Published history.

Content from different Threads accounts should never appear together.

Each calendar should remain completely independent.

---

# Stats Behaviour

Stats should analyse only the active account.

Examples include:

- Followers.
- Views.
- Engagement.
- Clicks.
- Consistency.
- Best-performing Writing Mode.
- Best-performing topics.

Stats should answer two questions:

"How is this account growing?"

and

"What has Aura AI learned from this account?"

---

# Learning Behaviour

Every published thread becomes feedback.

Aura AI should continuously learn from measurable signals such as:

- Views.
- Likes.
- Replies.
- Reposts.
- Clicks.
- Follower growth.

This learning should remain exclusive to the active account.

The objective is continuous improvement through observation rather than assumptions.

---

# Adaptive Behaviour

Aura AI should gradually adapt to each account over time.

Examples include:

- Better topic suggestions.
- Better Scout recommendations.
- Better writing preferences.
- Better tone selection.
- Better Writing Mode recommendations.

The more Aura AI learns,

the less manual configuration should be required from the creator.

---

# Future Expansion

Version 1 focuses exclusively on Threads.

Future versions may introduce additional platform behaviours for:

- X
- Facebook
- LinkedIn
- Pinterest
- Instagram
- TikTok
- YouTube

Each future platform should introduce its own independent behaviour model while preserving the same architecture.

Platform behaviour should be modular.

Never hardcoded.

---

# Platform Behaviour Checklist

Before generation begins, Aura AI should internally ask:

- Which account is currently active?
- Has the correct context been loaded?
- Are Scout recommendations relevant?
- Are writing preferences account-specific?
- Are Stats using the correct performance history?
- Is learning isolated to this account?

If any answer is "No",

Aura AI should reload the correct account context before continuing.

---

# Do

Aura AI should:

- Treat every account independently.
- Learn continuously.
- Adapt naturally.
- Protect account-specific context.
- Improve through measurable feedback.
- Refresh immediately after switching accounts.
- Maintain consistent behaviour.

---

# Don't

Aura AI should never:

- Mix account histories.
- Share Scout recommendations across accounts.
- Share writing preferences across accounts.
- Share analytics across accounts.
- Learn globally across unrelated accounts.
- Require repeated manual configuration.

Every account deserves its own AI experience.

---

# Engine Principle

Platform Behaviour is not about understanding Threads alone.

It is about understanding the creator behind each Threads account.

Every Active Account should feel like it has its own memory.

Its own history.

Its own learning.

Its own recommendations.

Its own growth journey.

HERO writes using the active account's context.

AURA validates using the active account's standards.

Aura AI learns from the active account's performance.

Switching the Active Account should never feel like changing profiles.

It should feel like activating another intelligent assistant that already understands that creator.
