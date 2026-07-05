# Features

Version: 1.0
Status: Locked
Last Updated: 2026-07-05

---

# Purpose

This document defines every core feature available in Aura AI Version 1.

Each feature exists to solve a specific creator problem while maintaining Aura AI's philosophy:

Reduce complexity.
Reduce decision fatigue.
Increase consistency.

Every feature should feel simple to use while hiding complex AI processes behind the scenes.

---

# Feature Overview

Aura AI Version 1 consists of six primary modules.

- Home
- Scout
- Write
- Planner
- Stats
- Profile

---

# Active Account

Aura AI operates using one Active Account at a time.

Version 1 supports:

- Multiple Threads accounts

Only one Threads account may be active at any given time.

Switching the Active Account updates every feature automatically.

Affected modules include:

- Home
- Scout
- Write
- Planner
- Stats

Users never need to choose the account repeatedly throughout the app.

---

# HOME

## Purpose

Home serves as the creator dashboard.

Rather than displaying excessive analytics, Home immediately answers one question:

"What should I do today?"

---

## Components

### Today's Mission

Displays the user's daily activity targets.

Example:

- Reply 5 posts
- Create 3 posts

Mission progress updates automatically.

Completed missions are checked automatically.

---

### Weekly Streak

Displays the user's current posting consistency.

Example:

🔥 6 Week Streak

Weekly Streak motivates creators to remain consistent without creating unnecessary pressure.

Missing one day should not automatically reset the streak.

---

### Yesterday's Performance

Displays yesterday's performance comparison.

Metrics include:

- Views
- Followers
- Clicks
- Current Draft Count

Only daily change is displayed.

The objective is helping creators notice progress rather than focusing on lifetime numbers.

---

### Top Performing Posts

Displays three permanent cards.

Top Views

Highest viewed post.

Purpose:

Understand what the algorithm prefers.

---

Top Engagement

Highest engagement post.

Purpose:

Understand what audiences interact with most.

---

Most Clicks

Highest direct product link clicks.

Purpose:

Understand which content converts best.

Whenever a new record replaces an existing Top Post, display:

NEW

to attract user attention.

---

# SCOUT

## Purpose

Scout automatically discovers conversations worth joining.

The objective is increasing account activity through valuable engagement.

Scout focuses on helping users build relationships rather than chasing viral posts.

---

## Scout Feed

Scout displays three opportunities simultaneously.

Recommended structure:

Post 1

Relevant niche + high engagement

Post 2

Relevant niche + high engagement

Post 3

Trending or viral discussion

Users may refresh individual opportunities at any time.

---

## AI Generated Reply

Each discovered post automatically includes an AI-generated reply.

Reply Rules:

- One paragraph only
- 2–3 sentences
- Natural human writing
- No AI sounding language
- No hashtags
- No emoji spam
- No CTA

Replies should contribute value to the conversation.

Replies may:

- Add perspective
- Share experience
- Expand ideas
- Respectfully disagree
- Continue discussion

Replies should never feel promotional.

---

## Actions

Each Scout card includes:

Approve

Immediately:

- Publish reply
- Like post
- Repost post

---

Regenerate

Generate a different reply.

---

Refresh

Replace only that Scout card with a new opportunity.

---

Bookmark

Save the original post for future reference.

Only the original post is bookmarked.

Generated replies are never bookmarked.

---

# WRITE

## Purpose

Write is Aura AI's primary content generation feature.

Users provide simple inputs.

HERO generates.

AURA validates.

Approved content is returned.

---

## Input Form

Writing Mode

- Selling
- Informative
- Engagement

---

Topic

Free text.

Placeholder suggestions disappear when users begin typing.

---

How Many Threads

Options:

- 1
- 3
- 5
- 10

---

Advanced Settings

Language

Automatically remembers frequently used languages.

Default:

English

---

Tone

Options:

- Casual
- Professional

Default:

Casual

---

Product Link (Optional)

Users may insert a direct promotion link.

---

Link in Bio

Optional toggle.

When enabled, HERO naturally references the creator's bio rather than aggressively promoting products.

If both Link in Bio and Product Link are enabled:

HERO blends both naturally.

CTA should always remain curiosity-driven.

---

## Smart Defaults

Aura AI remembers previous generation preferences.

Examples:

- Writing Mode
- Language
- Tone

Returning users should rarely need to configure settings again.

---

## Generation Flow

Fill Form

↓

Generate

↓

HERO

↓

AURA

↓

Approved Content

---

## Generated Threads

Each generated thread includes:

Edit

Allows users to edit any post.

Once edited, the thread enters Draft Mode.

AURA no longer validates manually edited drafts.

---

Post Now

Immediately publishes the thread.

---

Save Draft

Stores the thread inside Planner.

---

Schedule Post

Opens:

Calendar

+

Time Picker

After confirmation:

Aura AI publishes automatically at the scheduled time.

---

# PLANNER

## Purpose

Planner functions as Aura AI's Content Calendar.

It helps creators organise future publishing while maintaining consistency.

---

## Calendar Views

Available views:

- Daily
- Weekly
- Monthly

---

## Calendar Indicators

Each date displays activity using coloured indicators.

Legend:

🔵 Published Posts

🟣 Replies / Engagement

🟢 Scheduled Posts

⚪ No Activity

Indicators provide a quick overview without cluttering the calendar.

---

## Date View

Selecting a date opens:

Posts

Replies

Scheduled Posts

Create Post

Users may immediately create new content from any date.

The Create Post button redirects directly to Write.

---

## Draft Section

Planner includes a Draft section.

Saved drafts remain here until users choose:

- Post Now
- Schedule Post

Drafts never publish automatically.

---

# STATS

## Purpose

Stats provides creators with meaningful performance insights.

Statistics should help creators improve rather than overwhelm them.

---

## Time Range

Users may switch between:

- Weekly
- Monthly

---

## Available Metrics

Followers

Increase or decrease.

---

Views

Overall account visibility.

---

Clicks

Direct product link clicks.

---

Account Activity

Measures overall creator activity.

Includes:

- Posts
- Replies

---

Engagement

Combines:

- Likes
- Replies
- Reposts

---

Consistency Score

Measures creator consistency.

Factors include:

- Posting frequency
- Reply activity
- Mission completion
- Scheduled content consistency

---

Top Topics

Displays topics generating the strongest performance.

---

Best Performing Writing Mode

Displays which Writing Mode consistently performs best.

---

AI Recommendation

Aura AI analyses creator behaviour.

Examples:

"Your Selling posts consistently outperform Informative posts."

or

"You haven't posted for three days."

Recommendations should remain practical and actionable.

---

# PROFILE

## Purpose

Profile manages Aura AI preferences.

It is not the user's social media profile.

---

## Components

Profile Information

Aura AI account details.

---

Connected Accounts

Displays all connected Threads accounts.

Only one account may remain Active.

Changing the Active Account updates every feature throughout the application.

---

Settings

Application preferences.

---

Subscription

Manage current subscription.

---

Appearance

Light Mode

Dark Mode

---

Logout

Safely logs out of Aura AI.

---

# Future Expansion

Version 1 focuses exclusively on Threads.

Future versions may introduce additional platforms.

The current architecture is designed to support future expansion without changing existing user workflows.

---

# Engine Principle

Every feature should remove decisions—not create more.

Users should spend their time creating and engaging.

Aura AI should handle everything else.
