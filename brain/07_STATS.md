# Stats Feature

Version: 1.0
Status: Locked
Last Updated: 2026-07-06

---

# Identity

Stats is Aura AI's analytics feature.

Its responsibility is helping creators understand account performance through structured metrics and AI-generated insights.

Stats does not generate content.

Stats does not manage publishing.

Stats helps creators interpret performance data.

---

# Purpose

The Stats feature transforms performance data into meaningful insights.

Its objective is helping creators understand what is working, what is changing, and where attention may be needed.

Creators should spend less time interpreting numbers and more time improving their content.

---

# Inputs

Stats receives creator actions.

Possible inputs include:

- Open Stats.
- Select a metric.
- Request AI analysis.

Every analysis begins with creator interaction.

---

# Outputs

Stats returns:

- Performance metrics.
- Detailed metric information.
- AI-generated insights.

AI analysis should only be generated when requested by the creator.

---

# Core Principle

Stats should present information before providing interpretation.

Creators should always see their performance data first.

AI analysis should remain optional and creator-controlled.

---

# Feature Flow

Every analytics request follows the same workflow.

```
Creator

↓

Open Stats

↓

Display Dashboard

↓

Select Metric

↓

Generate Analysis

↓

Display Insight
```

The dashboard should never trigger AI analysis automatically.

Analysis begins only after the creator selects a metric.



---

# Stats Workflow

Every analytics session begins with the performance dashboard.

The dashboard provides creators with a high-level overview of account performance.

No AI analysis should occur at this stage.

---

# Dashboard Overview

The dashboard displays the creator's primary performance metrics.

Examples include:

- Likes
- Replies
- Reposts
- Followers
- Engagement

The dashboard should remain lightweight and easy to scan.

Its purpose is presenting information,

not interpreting it.

---

# Metric Details

Selecting a metric opens a detailed view.

The detailed view may include:

- Performance trend.
- Top contributing posts.
- Historical activity.
- Metric breakdown.

Detailed information should always be displayed before AI analysis begins.

---

# AI Analysis

Creators may request AI analysis after reviewing the metric details.

AI analysis should explain:

- What changed.
- Possible contributing factors.
- Relevant observations.

AI analysis should always be based on the selected metric.

No analysis should be generated automatically.

---

# Workflow Completion

The analytics workflow is complete when:

- The creator finishes reviewing the metric.
- The creator closes the detailed view.
- The creator selects another metric.

Each selected metric begins a new analytics workflow.

---

# Workflow Principles

Stats should separate information from interpretation.

Creators should first understand the data.

AI should then help explain the data when requested.

This approach keeps analytics fast, transparent, and creator-controlled.



---

# Analytics Behaviour

Stats separates performance data from AI interpretation.

Performance data should always be displayed first.

AI insights should only appear when requested by the creator.

---

# Performance Overview

Every metric should begin with a factual overview.

The overview may include:

- Current value.
- Historical trend.
- Top contributing posts.
- Performance breakdown.

The overview should present facts without interpretation.

---

# AI Insights

After reviewing the performance overview,

the creator may request AI insights.

AI insights should help explain:

- Significant changes.
- Performance patterns.
- Content observations.
- Audience behaviour.

Insights should provide context,

not assumptions.

---

# Recommendations

When appropriate,

AI may provide actionable recommendations.

Recommendations should:

- Be specific.
- Be practical.
- Be relevant to the selected metric.

Recommendations should encourage improvement without overwhelming the creator.

Examples include:

> "Your engagement has gradually declined over the past week. Maintaining consistent posting and participation in discussions generally produces stronger long-term growth on Threads."

> "Your replies generated more engagement than your original posts this week. Consider participating in more relevant conversations to maintain momentum."

Recommendations should remain supportive and professional.

---

# Positive Reinforcement

When performance improves,

AI should acknowledge meaningful progress.

Examples include:

> "Great work! Your engagement has increased compared to last week. Your recent posting consistency appears to be contributing to stronger audience interaction."

Positive reinforcement should celebrate progress without exaggeration.

---

# Behaviour Principles

Stats should help creators understand performance,

not judge it.

Every insight should be factual,

constructive,

and actionable.

The objective is building better long-term habits,

not creating unnecessary pressure.


---

# Insight Generation

AI insights begin only after the creator explicitly requests analysis for a selected metric.

Each analysis should focus only on the selected metric.

The Stats feature should never generate unrelated observations.

---

# Analysis Workflow

Every AI analysis follows the same workflow.

```
Creator Selects Metric

↓

Load Metric Details

↓

Request Analysis

↓

Stats Brain

↓

Display Insight
```

Only completed insights should be displayed to the creator.

---

# Analysis Scope

Each analysis should remain focused.

Analysis may include:

- Performance changes.
- Historical trends.
- Top contributing posts.
- Relevant observations.
- Practical recommendations.

Analysis should never extend beyond the selected metric unless explicitly requested by the creator.

---

# Context Awareness

Stats Brain should analyse performance using the Active Account.

Analysis should consider:

- Account history.
- Recent performance.
- Current trends.
- Selected metric.

Every insight should be relevant to the creator's current account.

---

# Insight Consistency

AI insights should always remain consistent with the displayed performance data.

Insights should explain the data,

never contradict it.

Recommendations should always be supported by observable account performance.

---

# Analysis Principles

Stats should explain performance,

not speculate about it.

Insights should remain factual,

objective,

and actionable.

Every recommendation should be grounded in the creator's available performance data.



---

# Failure Rules

The Stats feature should stop the current analysis whenever required performance data is unavailable.

Examples include:

- Performance data unavailable.
- Selected metric not found.
- Analysis request invalid.
- Incomplete analytics data.

Stats should never generate insights using incomplete or unreliable data.

---

# Retry Rules

Retry should occur only when the failure is temporary.

Examples include:

- Temporary data loading interruption.
- Temporary analysis interruption.
- Temporary processing issue.

Retry should never occur when additional creator action is required.

If the creator needs to select another metric or provide additional input,

the current analysis should stop until the request is complete.

---

# Design Principles

Stats should always:

- Present data clearly.
- Keep analytics easy to understand.
- Separate information from interpretation.
- Give creators control over AI analysis.

Creators should decide when deeper analysis is needed.

Aura AI should provide insights only when requested.

---

# Engine Principle

Stats is Aura AI's analytics workflow.

It does not generate content.

It does not perform content reasoning.

It does not modify creator data.

Its responsibility is presenting performance information and coordinating AI-powered analysis through the Stats Brain when requested by the creator.

---

# Final Statement

Stats exists to help creators understand their performance with confidence.

Performance data should always be transparent.

AI insights should always remain factual, objective, and grounded in observable account activity.

The dashboard informs.

The creator decides.

Aura AI helps explain.
