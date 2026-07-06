# Features

Version: 1.1
Status: Locked
Last Updated: 2026-07-06

---

# Purpose

This document defines every core feature available in Aura AI Version 1.

Each feature exists to solve a specific creator problem while supporting Aura AI's core philosophy:

- Reduce complexity.
- Reduce decision fatigue.
- Increase consistency.

Every feature should remain simple to use while hiding AI complexity behind the scenes.

Users interact with Aura AI.

They never interact directly with the internal AI components.

---

# Feature Overview

Aura AI Version 1 consists of six primary modules.

- Home
- Scout
- Write
- Planner
- Stats
- Profile

Each module has one clearly defined responsibility.

No feature should attempt to perform another feature's responsibility.

---

# Active Account

Aura AI always operates using one Active Account.

Version 1 supports:

- Multiple Threads accounts

Only one Threads account may remain active at any given time.

Switching the Active Account automatically updates every AI-powered feature throughout the application.

Affected modules include:

- Home
- Scout
- Write
- Planner
- Stats

Users should never need to manually select their account while using individual features.

---

# AI Context

Every Active Account maintains its own independent AI context.

This includes:

- Writing behaviour.
- Scout behaviour.
- Historical performance.
- Draft history.
- Scheduled content.
- AI learning.

Switching the Active Account immediately replaces the entire AI context.

No behaviour, recommendations, or learning should ever be shared between different accounts.

Each account should gradually develop its own independent identity over time.

---

# HOME

## Purpose

Home serves as the creator dashboard.

Rather than displaying excessive analytics,

Home answers one simple question:

"What should I do today?"

Home is not an AI feature.

Its responsibility is presenting the most relevant information from across Aura AI in one place.

Any AI-generated recommendations displayed on Home originate from other specialised brains, such as Stats Brain.

Home itself performs no AI reasoning.

---

## Components

### Today's Mission

Displays the creator's daily activity targets.

Example:

- Reply to 5 posts.
- Create 3 posts.

Mission progress updates automatically.

Completed missions are checked automatically.

---

### Weekly Streak

Displays the creator's posting consistency.

Example:

🔥 6 Week Streak

Weekly Streak encourages long-term consistency without creating unnecessary pressure.

Missing one day should not automatically reset the streak.

---

### Yesterday's Performance

Displays yesterday's performance compared with the previous day.

Metrics include:

- Views
- Followers
- Clicks
- Current Draft Count

Only daily changes are displayed.

The objective is helping creators recognise progress rather than focusing on lifetime numbers.

---

### Top Performing Posts

Displays three permanent performance cards.

Top Views

The post with the highest number of views.

Purpose:

Understand what attracts the most visibility.

---

Top Engagement

The post with the highest engagement.

Purpose:

Understand what audiences interact with most.

---

Most Clicks

The post generating the highest number of product link clicks.

Purpose:

Understand which content drives the strongest conversions.

Whenever a new record replaces an existing top-performing post,

display:

NEW

to immediately attract the creator's attention.

---

## Behaviour Rules

Home should remain simple.

Home should never become an analytics dashboard.

Home should never overwhelm creators with excessive information.

Every component should help creators quickly understand:

- What happened yesterday.
- What needs attention today.
- Which content performs best.

The primary objective of Home is action rather than analysis.


---

# SCOUT

## Purpose

Scout automatically discovers valuable conversations worth joining.

Its objective is helping creators build genuine relationships through meaningful engagement rather than chasing viral posts.

Scout is powered by Scout Brain.

Scout Brain discovers relevant opportunities, generates natural replies, and submits every reply to AURA for quality review before presenting it to the creator.

Users should spend less time searching for conversations and more time participating in them.

---

## AI Responsibility

Scout Brain is responsible for:

- Discovering relevant conversations.
- Understanding discussion context.
- Selecting valuable engagement opportunities.
- Generating natural replies.
- Matching replies to the Active Account.

AURA is responsible for:

- Reviewing generated replies.
- Improving weak wording if necessary.
- Ensuring replies feel natural.
- Approving replies before presentation.

Creators never receive unreviewed AI replies.

---

## Scout Feed

Scout displays three engagement opportunities simultaneously.

Each opportunity includes:

- Original post.
- AI-generated suggested reply.
- Available actions.

The objective is helping creators engage immediately without needing to think about what to write.

Every suggested reply has already passed through AURA's review process.

---

## AI Workflow

Every Scout request follows the same execution flow.

```
Refresh Scout

↓

System Brain

↓

Load Active Account

↓

Load Relevant Knowledge

↓

Scout Brain

↓

Discover Opportunity

↓

Generate Reply

↓

AURA Review

↓

Suggested Reply

↓

User
```

The creator interacts only with the final suggested reply.

Scout Brain and AURA remain completely invisible.

---

## Actions

Each Scout card includes four actions.

---

### Approve

Immediately performs:

- Publish reply.
- Like original post.
- Repost original post.

The creator completes meaningful engagement with one action.

---

### Regenerate

Generate another reply for the current post.

Workflow:

```
Suggested Reply

↓

Regenerate

↓

Scout Brain

↓

Generate New Reply

↓

AURA Review

↓

Suggested Reply

↓

User
```

The original post remains unchanged.

Only the suggested



---

# WRITE

## Purpose

Write is Aura AI's primary AI content generation feature.

Creators provide simple inputs.

System Brain prepares the request.

HERO generates.

AURA validates.

The creator receives only approved content.

The objective is helping creators create high-quality social media content with minimal configuration.

---

## AI Responsibility

System Brain is responsible for:

- Understanding the request.
- Loading the Active Account.
- Loading relevant knowledge.
- Preparing the generation context.

HERO Brain is responsible for:

- Planning content strategy.
- Structuring the thread.
- Generating human-like writing.
- Following the selected Writing Mode.

AURA is responsible for:

- Reviewing generated content.
- Improving weak sections when necessary.
- Validating quality.
- Assigning Aura Score.
- Approving the final result.

---

## Input Form

### Writing Mode

Available options:

- Selling
- Informative
- Engagement

Writing Mode represents the creator's objective.

Aura AI always prioritises Writing Mode above all writing strategies.

---

### Topic

Free text.

Placeholder suggestions disappear when the creator begins typing.

The topic provides the primary direction for HERO.

---

### How Many Threads

Available options:

- 1
- 3
- 5
- 10

Every generated thread should provide a genuinely different strategic approach.

---

## Advanced Settings

Advanced Settings remain collapsed by default.

Only creators requiring additional control should expand them.

---

### Language

Aura AI remembers the creator's preferred language.

Default:

English

---

### Tone

Available options:

- Casual
- Professional

Default:

Casual

---

### Product Link

Optional.

When provided,

HERO naturally positions the product as the solution within Selling Mode.

---

### Link in Bio

Optional toggle.

When enabled,

HERO naturally references the creator's bio instead of aggressively promoting products.

If both Product Link and Link in Bio are enabled,

HERO blends both naturally while maintaining a curiosity-driven CTA.

---

## Smart Defaults

Aura AI automatically remembers frequently used preferences.

Examples include:

- Writing Mode.
- Language.
- Tone.

Returning creators should rarely need to reconfigure the same settings.

---

## AI Workflow

Every generation follows the same execution flow.

```
Fill Form

↓

Generate

↓

System Brain

↓

Load Active Account

↓

Load Relevant Knowledge

↓

HERO Brain

↓

AURA Validation

↓

Approved Content

↓

User
```

The creator interacts only with the final approved content.

All AI reasoning remains invisible.

---

## Generated Threads

Each approved thread includes the following actions.

---

### Edit

Allows creators to manually modify any post.

Once edited,

the thread enters Draft Mode.

Aura AI no longer validates manually edited drafts.

---

### Post Now

Immediately publishes the approved thread.

---

### Save Draft

Stores the approved thread inside Planner.

Saved drafts never publish automatically.

---

### Schedule Post

Opens:

- Calendar
- Time Picker

After confirmation,

Planner manages automatic publishing at the selected date and time.

---

## Behaviour Rules

Write should minimise creator decisions.

Aura AI automatically determines:

- Hook strategy.
- Thread structure.
- Reveal progression.
- CTA placement.
- Psychological flow.

Creators decide only:

- Topic.
- Writing Mode.
- Publish method.

Anything Aura AI can confidently determine should never become another user setting.



---

# PLANNER

## Purpose

Planner functions as Aura AI's Content Calendar.

Its responsibility is helping creators organise future publishing while maintaining consistency.

Planner focuses on visibility rather than decision making.

Creators remain fully responsible for planning their own publishing schedule.

---

## Components

### Calendar Views

Available views:

- Daily
- Weekly
- Monthly

---

### Calendar Indicators

Each date displays activity using coloured indicators.

Legend:

🔵 Published Posts

🟣 Replies / Engagement

🟢 Scheduled Posts

⚪ No Activity

Indicators provide an immediate overview without requiring creators to open individual dates.

---

### Date View

Selecting a date displays:

- Published Posts
- Replies
- Scheduled Posts
- Create Post

The Create Post button redirects directly to Write.

Planner never generates content automatically.

---

### Draft Section

Planner includes a dedicated Draft section.

Saved drafts remain here until the creator chooses:

- Post Now
- Schedule Post

Drafts never publish automatically.

---

## Behaviour Rules

Planner should remain simple.

Its responsibility is organisation rather than recommendation.

Creators should immediately recognise:

- Empty publishing days.
- Busy publishing days.
- Scheduled content.
- Published content.
- Engagement activity.

Planning decisions always remain with the creator.

---

# STATS

## Purpose

Stats helps creators understand why their performance changes.

Rather than overwhelming creators with analytics,

Stats combines performance metrics with AI-powered explanations.

Numbers provide visibility.

Stats Brain provides understanding.

---

## Stats Dashboard

The Stats Dashboard displays high-level performance metrics.

Available metrics include:

- Followers
- Views
- Likes
- Replies
- Clicks
- Account Activity
- Engagement
- Consistency Score

The Stats Dashboard should remain clean, simple, and easy to scan.

Its objective is helping creators quickly understand overall account performance.

Detailed AI analysis appears only after the creator selects an individual metric.

---

## Metric Details

Selecting any metric opens a dedicated details page.

Each details page displays:

- Historical trend.
- Top contributing posts.
- Performance comparison.
- AI-generated explanation.

Example:

```
Stats Dashboard

↓

+1.8K Likes

↓

Likes Details

↓

Top Contributing Posts

↓

AI Analysis
```

Example recommendation:

> Most of your likes come from educational threads explaining Pinterest strategies.

The objective is helping creators understand the reasons behind performance rather than simply displaying numbers.

---

## Top Topics

Displays topics generating the strongest overall performance.

The objective is helping creators identify recurring patterns rather than isolated successes.

---

## Best Performing Writing Mode

Displays which Writing Mode consistently performs best for the Active Account.

Examples:

- Selling
- Informative
- Engagement

This helps creators understand which objective resonates most with their audience.

---

## AI Analysis

Stats Brain performs analysis only when requested by the creator.

Aura AI should never overwhelm creators with unnecessary recommendations.

Instead,

AI analysis should appear naturally after the creator explores a specific metric.

Recommendations should always be:

- Practical.
- Evidence-based.
- Actionable.

The objective is improving future decision making rather than reporting historical numbers.

---

## Behaviour Rules

Stats should prioritise understanding over analytics.

Creators should leave the Stats page with a clear understanding of:

- What performed well.
- Why it performed well.
- What can be improved next.

---

# PROFILE

## Purpose

Profile manages Aura AI account settings.

It is not the creator's public social media profile.

---

## Components

### Profile Information

Displays Aura AI account details.

---

### Connected Accounts

Displays every connected Threads account.

Only one account may remain Active.

Changing the Active Account immediately updates every AI-powered feature throughout Aura AI.

---

### Settings

Application preferences.

---

### Subscription

Manage the current subscription.

---

### Appearance

Available options:

- Light Mode
- Dark Mode

Aura AI remembers the creator's preferred appearance automatically.

---

### Logout

Safely signs the creator out of Aura AI.

---

## Behaviour Rules

Profile centralises account management.

Creators should never manually manage AI behaviour.

Switching the Active Account should automatically update the entire Aura AI experience.

---

# Future Expansion

Version 1 focuses exclusively on Threads.

Future versions may introduce additional social media platforms.

The current architecture is designed to support expansion without changing existing user workflows.

Potential future platforms include:

- X
- Facebook
- Pinterest
- LinkedIn
- Instagram

New platforms should integrate through System Brain while preserving the same creator experience.

---

# Engine Principle

Every feature should remove decisions rather than create more.

Home provides clarity.

Scout discovers conversations.

Write creates content.

Planner organises publishing.

Stats explains performance.

Profile manages the creator's experience.

Behind every feature,

System Brain coordinates every request.

Aura Brain provides knowledge.

Specialised Brains perform feature-specific reasoning.

AURA protects quality whenever validation is required.

The creator experiences one intelligent assistant.

Aura AI handles the complexity behind the scenes.