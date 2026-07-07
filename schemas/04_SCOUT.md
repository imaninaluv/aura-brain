# Scout Schema

Version: 1.0
Status: Locked
Last Updated: 2026-07-07

---

# Purpose

The Scout Schema defines the AI-powered engagement workflow within Aura AI.

Its purpose is to continuously discover relevant Threads posts, generate high-quality replies, and present engagement opportunities to the creator without requiring manual searching.

Unlike the Thread Schema, Scout is not a permanent content object.

Instead, it represents a temporary AI workflow that continuously prepares engagement opportunities for the currently active Account Context.

---

# Definition

A Scout object represents a single engagement opportunity prepared by Aura AI.

Each Scout object consists of:

- One discovered Threads post.
- One AI-generated reply.
- Supporting AI analysis used internally to determine relevance.

Scout objects exist only to help the creator discover and participate in conversations efficiently.

If the creator decides not to reply, the Scout object is simply discarded.

Only successful replies become permanent business objects through the Reply Schema.

---

# Scope

The Scout Schema is used exclusively by the Scout feature.

It collaborates with:

- Account Context
- Reply
- Analysis
- Planner

Scout does not create Threads.

Scout does not manage Drafts.

Scout does not own publishing history.

Its responsibility ends once the creator either replies to the discovered post or moves on to another opportunity.

---

# Core Concept

Scout operates as a continuous opportunity discovery engine rather than a traditional search interface.

```
Background Scout Engine
          │
          ▼
Discover Relevant Post
          │
          ▼
Analyse Post
          │
          ▼
Generate Reply
          │
          ▼
Store in Opportunity Queue
          │
          ▼
Creator Opens Scout
          │
          ▼
Instant Display
```

Creators never search for conversations manually.

Instead, Aura AI continuously prepares relevant opportunities in the background based on the currently active Account Context.

The Scout interface simply presents the next available opportunity, creating an experience similar to swiping through short-form content while discovering conversations worth joining.


---

# Schema Overview

The Scout Schema represents a single engagement opportunity prepared by Aura AI.

Each Scout object combines a discovered Threads post with an AI-generated reply, allowing creators to engage immediately without waiting for analysis or content generation.

Scout objects are temporary by design.

They exist only to support the creator's current engagement session and are continuously replaced as new opportunities become available.

---

# Core Properties

Each Scout object contains the following information:

| Property | Description |
|----------|-------------|
| Scout ID | Unique identifier for the Scout opportunity. |
| Account Context ID | The Account Context for which the opportunity was generated. |
| Target Post ID | Identifier of the discovered Threads post. |
| Target Author | Creator of the discovered Threads post. |
| Target Content | Original Threads post content. |
| Target URL | Direct link to the original Threads post. |
| Opportunity Score | Internal AI ranking score used to prioritise opportunities. |
| Generated Reply | AI-generated reply prepared for the creator. |
| Generated At | Date and time the opportunity was prepared. |
| Expires At | Time after which the opportunity is considered stale and may be replaced. |

These properties allow Scout to present complete engagement opportunities instantly without requiring additional AI processing.

---

# Relationships

Every Scout object belongs to exactly one Account Context.

Relationship overview:

```
Account Context
        │
        ▼
     Scout
        │
        ├──────────────┐
        ▼              ▼
   Analysis        Reply
                        │
                        ▼
                    Planner
```

The Scout Schema collaborates with other business schemas as follows:

- Account Context determines the niche and creator context used for opportunity discovery.
- Analysis performs internal evaluation of discovered posts before an opportunity is presented.
- Reply creates a permanent business object only when the creator chooses to reply.
- Planner records the published reply after successful publication.

Scout itself does not store creator history.

Unused Scout opportunities are temporary and may be discarded without affecting any permanent business records.


---

# Lifecycle

Unlike other business objects, a Scout object follows a temporary lifecycle.

Its purpose is to provide an immediate engagement opportunity rather than becoming permanent creator data.

The typical lifecycle is:

```
Background Discovery
         │
         ▼
Find Relevant Post
         │
         ▼
Analyse Opportunity
         │
         ▼
Generate AI Reply
         │
         ▼
Store in Opportunity Queue
         │
         ▼
Present to Creator
         │
     ┌───┴───────────────┐
     ▼                   ▼
Swipe Away           Reply Published
     │                   │
     ▼                   ▼
Discard           Create Reply Object
```

Every Scout object eventually reaches one of two outcomes:

- Discarded after the creator skips the opportunity.
- Converted into a Reply when the creator publishes the generated reply.

Scout objects never become permanent business history.

---

# Ownership

Every Scout object belongs to exactly one Account Context.

Ownership hierarchy:

```
Aura User
      │
      ▼
Account Context
      │
      ▼
 Opportunity Queue
      │
      ▼
     Scout
      │
      ▼
     Reply
```

The Opportunity Queue exists only within its owning Account Context.

Each connected Threads account maintains its own independent queue of engagement opportunities.

Scout opportunities are never shared between Account Contexts.

---

# Opportunity Queue Lifecycle

Aura AI continuously maintains an Opportunity Queue for every active Account Context.

The queue contains a predefined number of ready-to-use Scout opportunities.

Each opportunity already includes:

- A discovered Threads post.
- Internal AI analysis.
- A fully generated AI reply.

This allows Scout to present engagement opportunities instantly without waiting for additional AI processing.

The Opportunity Queue follows these principles:

- Opportunities are prepared in the background.
- Swipe removes the current opportunity from the queue.
- Background processes replenish the queue whenever it falls below the minimum threshold.
- Unused opportunities remain available between sessions until they expire or become invalid.
- Expired or unavailable opportunities are automatically replaced with newly generated opportunities.

The creator never interacts with the queue directly.

Instead, Aura AI continuously manages it behind the scenes to provide a seamless browsing experience.


---

# Business Rules

The Scout Schema follows a set of rules that ensure engagement opportunities remain relevant, responsive, and consistent throughout the creator experience.

## Rule 1 — Automatic Opportunity Discovery

Creators never search for conversations manually.

Scout continuously discovers relevant Threads posts in the background using the currently active Account Context.

Opportunity discovery should consider factors such as:

- Account niche
- Previous creator content
- Audience relevance
- Engagement potential

The creator's only responsibility is to browse the prepared opportunities.

---

## Rule 2 — One Opportunity, One Reply

Each Scout opportunity contains:

- One discovered Threads post.
- One AI-generated reply.

If the creator requests another reply, the previous generated reply is discarded and replaced with a newly generated reply.

Scout never stores multiple reply variations for the same opportunity.

---

## Rule 3 — Scout Does Not Create History

Scout opportunities are temporary.

Browsing,

swiping,

or regenerating replies should never create permanent business records.

Only when the creator successfully publishes a reply does Aura AI create a Reply object and record it within Planner.

---

## Rule 4 — Continuous Opportunity Queue

Aura AI should continuously maintain a ready-to-use Opportunity Queue for each Account Context.

The queue should always contain prepared engagement opportunities whenever possible.

Unused opportunities may remain available across multiple sessions until they:

- expire,
- become invalid,
- are consumed,
- or no longer satisfy Scout's ranking criteria.

Queue management is handled entirely by Aura AI without requiring creator interaction.

---

## Rule 5 — Independent Account Contexts

Each Account Context maintains its own independent Scout experience.

Opportunity discovery,

generated replies,

and queue management must remain completely isolated between different Account Contexts.

Browsing opportunities for one Threads account must never influence another connected Threads account.

---

# Validation Rules

Before presenting a Scout opportunity, Aura AI should validate that:

- A valid Account Context is active.
- The discovered Threads post is still available.
- The generated reply has been successfully prepared.
- The opportunity has not expired.
- The opportunity satisfies the minimum quality requirements for presentation.

Before publishing a reply, Aura AI should additionally verify that:

- The connected Threads account is available.
- The reply can be published successfully.
- The target Threads post is still accessible.

If validation fails, the affected opportunity should be discarded and automatically replaced by a newly prepared opportunity.

These validation rules ensure Scout consistently delivers high-quality, ready-to-use engagement opportunities while maintaining a seamless creator experience.


---

# Business Examples

The following examples demonstrate how the Scout Schema behaves during normal creator workflows.

### Example 1 — Instant Opportunity Discovery

A creator opens the Scout feature.

Instead of waiting for a search to complete, Aura AI immediately presents a prepared engagement opportunity.

The creator sees:

- One relevant Threads post.
- One AI-generated reply.

No manual searching or additional AI generation is required before browsing begins.

---

### Example 2 — Browsing Opportunities

The creator decides not to engage with the current post.

They simply swipe to the next opportunity.

Aura AI immediately displays another prepared Threads post with its corresponding AI-generated reply.

The skipped opportunity is discarded.

No business history is created.

The creator may continue browsing indefinitely while Aura AI replenishes new opportunities in the background.

---

### Example 3 — Publishing a Reply

The creator finds a suitable opportunity and publishes the generated reply.

Scout immediately completes its responsibility.

Aura AI then:

- Creates a Reply business object.
- Records the published reply inside Planner.
- Makes the reply available for future reporting and analytics.

The original Scout opportunity is no longer required after publication.

---

# Design Rationale

The Scout Schema is designed around proactive engagement rather than reactive searching.

Instead of asking creators to search for conversations manually, Aura AI continuously discovers relevant opportunities and prepares complete replies before they are needed.

This architecture provides:

- Instant browsing experience.
- Reduced waiting time.
- Consistent AI quality.
- Minimal creator effort.
- Continuous engagement opportunities.

By separating temporary Scout opportunities from permanent Reply records, Aura AI avoids storing unnecessary AI-generated content while preserving meaningful creator actions.

---

# Final Statement

The Scout Schema represents Aura AI's proactive engagement engine.

It continuously discovers relevant conversations, prepares complete engagement opportunities, and delivers them instantly through a seamless browsing experience.

Scout exists only to support the creator's current decision-making process.

Only when the creator chooses to publish a reply does Aura AI create a permanent business record.

This separation allows Scout to remain lightweight, responsive, and continuously adaptive while keeping the platform's permanent business data focused solely on meaningful creator actions.
