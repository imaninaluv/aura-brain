# Shared Rules

Version: 1.0
Status: Locked
Last Updated: 2026-07-06

---

# Identity

Shared Rules defines the universal operating principles followed by every Aura AI brain and feature.

Its responsibility is ensuring consistent behaviour across the entire AI system.

Shared Rules does not perform reasoning.

Shared Rules does not generate outputs.

It establishes the standards that every AI component must follow.

---

# Purpose

The purpose of Shared Rules is maintaining consistency, reliability, and predictability throughout Aura AI.

Every brain should solve different problems,

but they should all follow the same operating principles.

---

# Scope

Shared Rules applies to:

- System Brain
- HERO Brain
- AURA
- Scout Brain
- Write Feature
- Planner Feature
- Stats Feature
- Future AI components

No AI component is exempt from these rules.

---

# Core Principle

Every AI component should focus on one clear responsibility.

Responsibilities should never overlap.

Shared Rules exists to ensure every component behaves consistently regardless of its purpose.

---

# Rule Hierarchy

When conflicts occur,

Shared Rules always takes priority over individual component behaviour.

Component-specific rules may extend Shared Rules,

but they should never contradict them.


---

# Single Responsibility

Every Aura AI component should perform one primary responsibility.

Responsibilities should never overlap.

When additional functionality is required,

the appropriate component should be used instead.

---

# Respect Creator Intent

Every request should prioritise the creator's current objective.

AI should never replace the creator's intent with its own assumptions.

When uncertainty exists,

the system should request clarification rather than guess.

---

# Active Account Awareness

Every AI-powered request should operate using the currently active account.

Reasoning,

analysis,

and recommendations should always reflect the Active Account Context.

No request should use data from another account.

---

# Execution Context

Every AI component should rely only on the provided Execution Context.

Components should never independently retrieve:

- Account data.
- Knowledge.
- Creator history.
- Platform information.

All required context should be prepared before execution begins.

---

# No Assumptions

AI should never fabricate,

guess,

or invent missing information.

When required information is unavailable,

execution should stop or request additional creator input.

---

# Consistent Behaviour

The same request,

using the same context,

should always follow the same execution process.

Differences in output should result from AI reasoning,

not inconsistent system behaviour.


---

# Standard Execution Flow

Every AI-powered request should follow the standard execution pipeline.

```
Creator Request

↓

Prepare Context

↓

Execute

↓

Validate (When Required)

↓

Return Result
```

No component should skip required stages.

---

# No Component Bypass

Every component should perform only its assigned responsibility.

Components should never bypass another required component.

Examples include:

- HERO should not bypass AURA validation.
- Scout should not load knowledge independently.
- Planner should not edit content.
- Stats should not analyse data before a metric has been selected.

Every request should respect the established execution pipeline.

---

# Knowledge Usage

Knowledge should only be used when relevant to the current request.

Components should never load unnecessary knowledge.

Using only the required knowledge improves consistency,

performance,

and maintainability.

---

# Validation Requirements

Whenever validation is required,

generated outputs should always pass through AURA before reaching the creator.

Examples include:

- Thread generation.
- Reply generation.

Components should never return unvalidated generated content.

---

# Error Handling

When execution cannot continue,

components should stop gracefully.

AI should never continue using incomplete,

invalid,

or unreliable information.

If recovery is not possible,

control should return to the appropriate component or request additional creator input.

---

# Execution Principles

Every execution should remain:

- Predictable.
- Consistent.
- Reliable.
- Fully traceable through the established workflow.

No component should introduce unexpected behaviour outside its defined responsibility.


---

# System Integrity

Every Aura AI component should preserve the integrity of the overall system architecture.

Components should remain independent while cooperating through the established execution pipeline.

No component should assume responsibilities that belong to another component.

---

# Scalability

Shared Rules should support future expansion.

New features,

brains,

knowledge modules,

or platforms should extend the existing architecture without requiring fundamental changes to the operating principles.

Core behaviour should remain stable as the system grows.

---

# Extensibility

New AI components should integrate by following Shared Rules.

They should:

- Respect the execution pipeline.
- Use the provided Execution Context.
- Follow established validation requirements.
- Maintain a single responsibility.

Existing components should not require modification when new components are introduced.

---

# Consistency

Every creator should experience consistent behaviour throughout Aura AI.

Regardless of the feature being used,

the system should behave predictably,

follow the same principles,

and maintain the same quality standards.

Consistency should be treated as a core system requirement.

---

# Maintainability

Shared Rules should make Aura AI easier to maintain over time.

Responsibilities should remain clearly separated.

Rules should be defined once and reused throughout the system.

Duplicate operating rules should be avoided whenever possible.

---

# Integrity Principles

A well-designed AI system is built on consistency,

not complexity.

Shared Rules exists to ensure that every component behaves as part of one unified system,

regardless of how many features or AI components are added in the future.


---

# Failure Rules

Shared Rules should never be bypassed.

When a component cannot comply with these rules,

execution should stop until the issue has been resolved.

No component should continue by violating established operating principles.

---

# Rule Evolution

Shared Rules should evolve carefully.

New rules may be introduced when necessary,

but existing rules should remain stable whenever possible.

Changes should improve the overall architecture without creating conflicts or unnecessary complexity.

---

# Design Principles

Shared Rules should always promote:

- Consistency.
- Simplicity.
- Reliability.
- Scalability.
- Maintainability.

Every rule should make Aura AI easier to understand,

easier to extend,

and easier to maintain.

---

# System Principle

Shared Rules represents the operating standards of Aura AI.

It does not coordinate execution.

It does not generate outputs.

It does not perform validation.

Its responsibility is ensuring that every component follows the same architectural principles while remaining focused on its own responsibility.

---

# Final Statement

Shared Rules exists to provide one consistent foundation for every Aura AI component.

As the platform grows,

new features,

new brains,

and new capabilities should extend these rules rather than replace them.

A strong AI system is built through clear responsibilities,

consistent behaviour,

and disciplined architecture.

Shared Rules ensures every component works together as one unified system.