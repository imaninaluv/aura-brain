# Stats Schema

Version: 1.0
Status: Locked
Last Updated: 2026-07-07

---

# Purpose

The Stats Schema defines performance tracking and historical analytics within Aura AI.

Its purpose is to provide creators with a clear understanding of how their Threads account evolves over time by presenting meaningful performance metrics collected from published content.

Rather than generating analytics itself, the Stats Schema organises historical account data into actionable insights that help creators evaluate growth and content performance.

---

# Definition

The Stats Schema represents the creator's performance dashboard.

It tracks historical account metrics and publishing performance for the currently active Account Context.

The Stats dashboard focuses on measuring account growth rather than AI activity.

Examples include:

- Follower growth
- Views
- Likes
- Replies
- Reposts
- Link clicks
- Published Threads
- Published Replies

All metrics are presented as historical trends, allowing creators to compare performance across different time periods.

---

# Scope

The Stats Schema collaborates with multiple business schemas throughout Aura AI.

These include:

- Account Context
- Thread
- Reply
- Planner

Stats is responsible for:

- Displaying historical account performance.
- Tracking publishing activity.
- Showing performance trends over time.
- Comparing historical performance across different periods.
- Highlighting top-performing published content.

Stats does not generate content.

Stats does not perform AI analysis.

Stats does not influence publishing decisions.

Its responsibility is limited to collecting, organising, and presenting historical performance data in a meaningful way.

---

# Core Concept

Aura AI separates creator activity from creator performance.

```
Published Content
        │
        ▼
Threads Platform
        │
        ▼
Performance Data
        │
        ▼
Historical Snapshots
        │
        ▼
Stats Dashboard
```

Rather than displaying only the latest account numbers, Aura AI preserves historical snapshots of account performance.

These snapshots allow creators to:

- Monitor long-term account growth.
- Compare weekly, monthly, and yearly performance.
- Identify top-performing content.
- Understand publishing trends over time.

By focusing on historical progression instead of isolated metrics, the Stats dashboard provides creators with a more complete picture of their account's overall growth.



---

# Schema Overview

The Stats Schema provides a historical view of account performance for the currently active Account Context.

Rather than storing content itself, Stats collects historical performance snapshots and organises them into meaningful trends, comparisons, and performance summaries.

Every metric displayed within the Stats dashboard originates from published account activity.

Stats does not modify business objects.

Instead, it measures how those business objects perform over time.

---

# Core Properties

Each historical snapshot contains the information required to measure account performance at a specific point in time.

Core properties include:

| Property | Description |
|----------|-------------|
| Snapshot ID | Unique identifier for the historical snapshot. |
| Account Context ID | The Account Context associated with the performance data. |
| Snapshot Date | Date and time the performance snapshot was collected. |
| Followers | Total followers at the time of collection. |
| Views | Total account views recorded during the reporting period. |
| Likes | Total likes received during the reporting period. |
| Replies | Total replies received during the reporting period. |
| Reposts | Total reposts received during the reporting period. |
| Link Clicks | Total profile link clicks recorded during the reporting period. |
| Published Threads | Number of Threads published during the reporting period. |
| Published Replies | Number of Replies published during the reporting period. |

These properties provide sufficient historical information for trend analysis without duplicating business content.

---

# Relationships

Every Stats record belongs to exactly one Account Context.

Relationship overview:

```
Account Context
        │
        ▼
      Stats
   ┌────┼────┐
   ▼    ▼    ▼
Thread Reply Planner
```

Relationship behaviour includes:

- Thread contributes publishing activity.
- Reply contributes engagement activity.
- Planner provides historical publishing references.
- Account Context defines which Threads account the statistics belong to.

Stats never owns Threads or Replies.

Instead, it aggregates historical performance data and presents it as trends, comparisons, and performance summaries while preserving the original business objects as the single source of truth.



---

# Lifecycle

Unlike business objects such as Threads or Replies, the Stats Schema represents the continuous collection of historical account performance.

Each performance snapshot captures the state of the creator's Threads account at a specific point in time.

The typical lifecycle is:

```
Published Activity
        │
        ▼
Threads Platform
        │
        ▼
Scheduled Data Sync
        │
        ▼
Historical Snapshot
        │
        ▼
Stats Dashboard
```

As additional snapshots are collected over time, Aura AI builds a complete historical record of account performance.

Rather than replacing previous values, every new snapshot extends the account's performance history.

---

# Ownership

Every historical snapshot belongs to exactly one Account Context.

Ownership hierarchy:

```
Aura User
      │
      ▼
Account Context
      │
      ▼
 Historical Snapshots
      │
      ▼
     Stats
```

Historical snapshots are isolated between Account Contexts.

Each connected Threads account maintains its own independent performance history.

Statistics collected for one account must never appear within another Account Context.

---

# Historical Snapshot Behaviour

Aura AI collects performance snapshots at regular intervals.

Each snapshot preserves the account's performance at the moment it is collected.

Historical snapshots are cumulative.

New snapshots never overwrite previous records.

Instead, Aura AI continuously extends the account's historical timeline.

These snapshots become the foundation for:

- Performance graphs.
- Weekly comparisons.
- Monthly comparisons.
- Yearly comparisons.
- Growth trends.
- Top-performing content.

Because every comparison references historical snapshots rather than live account values, creators can accurately evaluate long-term account performance without losing historical context.


---

# Business Rules

The Stats Schema follows a set of rules that ensure account performance remains accurate, consistent, and historically reliable.

## Rule 1 — Historical Data Is Permanent

Every historical snapshot represents the state of the creator's account at a specific point in time.

Historical snapshots should never overwrite or replace previous snapshots.

Each newly collected snapshot extends the account's historical timeline.

---

## Rule 2 — Statistics Are Read-Only

Stats exists solely to present account performance.

Creators cannot modify, edit, or manually adjust statistical data within Aura AI.

All displayed metrics must originate from validated account performance data.

---

## Rule 3 — Comparisons Use Historical Snapshots

Performance comparisons must always be calculated using historical snapshots.

Supported comparison periods include:

- Weekly
- Monthly
- Yearly

Comparisons should never rely solely on the account's latest metrics.

---

## Rule 4 — Top Performing Content Uses Published Results

Only successfully published Threads and published Replies are eligible for performance rankings.

Drafts,

scheduled content,

or unpublished work must never appear within performance summaries.

Top-performing content may include rankings such as:

- Most Views
- Most Likes
- Most Replies
- Most Link Clicks

---

## Rule 5 — Statistics Remain Isolated Per Account Context

Every Account Context maintains an independent performance history.

Historical snapshots,

comparisons,

graphs,

and performance rankings must remain isolated between connected Threads accounts.

Statistics from one account must never appear within another Account Context.

---

# Validation Rules

Before displaying statistics, Aura AI should validate that:

- A valid Account Context is active.
- Historical snapshots are available for the selected reporting period.
- Performance metrics originate from successful synchronisation with the connected Threads account.
- Published Threads and Replies reference valid business objects.

Before generating comparisons or trend analysis, Aura AI should additionally verify that:

- Historical snapshots exist for both comparison periods.
- Performance calculations are based on complete historical data.

If sufficient historical data is unavailable, Aura AI should continue displaying the available statistics while clearly omitting unsupported comparisons.

These validation rules ensure that every graph, comparison, and performance summary accurately reflects the creator's historical account performance.


---

# Business Examples

The following examples demonstrate how the Stats Schema behaves during normal creator workflows.

### Example 1 — Daily Performance Synchronisation

Aura AI performs a scheduled synchronisation with the connected Threads account.

A new historical snapshot is created containing the account's latest performance metrics, including:

- Followers
- Views
- Likes
- Replies
- Reposts
- Link Clicks
- Published Threads
- Published Replies

The previous historical snapshots remain unchanged.

The new snapshot extends the account's performance history.

---

### Example 2 — Monthly Performance Comparison

A creator opens the Stats dashboard and selects **Monthly Comparison**.

Aura AI retrieves the historical snapshots for the current month and the previous month.

The dashboard presents changes in account performance, including:

- Follower growth
- Engagement changes
- Publishing activity
- Overall account trends

The comparison is generated entirely from historical snapshots without modifying the underlying business data.

---

### Example 3 — Reviewing Top Performing Content

A creator opens the **Top Performing Posts** section.

Aura AI analyses published content and displays rankings such as:

- Most Viewed
- Most Liked
- Most Replied
- Most Link Clicks

Only successfully published Threads and Replies are considered.

Drafts and unpublished content are excluded from performance rankings.

---

# Design Rationale

The Stats Schema is designed around historical progression rather than isolated metrics.

Instead of presenting only the account's current performance, Aura AI preserves historical snapshots that allow creators to understand how their account evolves over time.

By separating raw historical data from calculated insights such as graphs, comparisons, and rankings, the platform maintains a clean architecture while supporting future analytical features without requiring changes to the underlying schema.

This approach provides:

- Reliable long-term performance tracking.
- Accurate historical comparisons.
- Consistent account reporting.
- Meaningful trend analysis.
- A stable analytical foundation for future platform growth.

---

# Final Statement

The Stats Schema represents Aura AI's historical performance layer.

It preserves the evolution of every connected Threads account through historical snapshots, allowing creators to measure growth, evaluate publishing performance, and identify long-term trends.

By treating historical data as the foundation for all analytical features, Aura AI delivers meaningful performance insights while maintaining a clear separation between business objects, publishing workflows, and account analytics.