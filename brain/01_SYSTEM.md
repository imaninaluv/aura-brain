# System Brain

Version: 1.0
Status: Locked
Last Updated: 2026-07-06

---

# Purpose

System Brain is Aura AI's central decision engine.

Its responsibility is to understand every creator request, determine the correct execution path, coordinate specialised brains, and return a validated response.

System Brain never generates content.

System Brain never analyses performance.

System Brain never discovers opportunities.

System Brain only thinks, decides, coordinates, and executes.

---

# Responsibilities

System Brain is responsible for:

- Receiving every creator request.
- Identifying user intent.
- Determining the requested feature.
- Loading the Active Account.
- Loading relevant knowledge.
- Selecting specialised brains.
- Coordinating execution order.
- Passing output to AURA.
- Returning approved results.

System Brain should never perform responsibilities belonging to another specialised brain.

---

# Core Principle

Every request follows the same philosophy.

```
Receive

↓

Understand

↓

Decide

↓

Load

↓

Execute

↓

Validate

↓

Return
```

No request should skip this process.

---

# Decision Pipeline

Every creator request enters the same decision pipeline.

```
Creator Request

↓

Identify Intent

↓

Identify Feature

↓

Load Active Account

↓

Load Required Knowledge

↓

Select Brain

↓

Execute

↓

AURA Validation

↓

Return Result
```

This pipeline applies to every AI-powered feature.

Only the selected specialised brain changes.

---

# Intent Detection

The first responsibility is determining what the creator wants.

Possible intents include:

- Write Content
- Scout Conversations
- Analyse Performance
- View Dashboard
- Manage Planner
- Update Profile

Intent should always be identified before any reasoning begins.

Unknown requests should never proceed to execution.

---

# Feature Selection

Once intent is identified,

System Brain selects the appropriate feature.

Examples:

Write

↓

HERO

---

Scout

↓

Scout Brain

---

Stats

↓

Stats Brain

---

Planner

↓

Planner Brain

---

Profile

↓

Profile System

Only one primary specialised brain should execute a request unless collaboration is explicitly required.



---

# Active Account Loading

Every request must begin by loading the Active Account.

```
INPUT

↓

Creator Request

↓

PROCESS

Retrieve Active Account

↓

OUTPUT

Active Account Context
```

The Active Account Context should include:

- Account Identity
- Account Type
- Historical Behaviour
- Historical Performance
- Connected Platform
- Current AI Context

No AI reasoning should begin before the Active Account Context is successfully loaded.

---

# Knowledge Loading

Knowledge should never be loaded all at once.

System Brain loads only the knowledge required for the current request.

```
INPUT

↓

Feature Request

↓

PROCESS

Select Required Knowledge

↓

OUTPUT

Knowledge Context
```

Example:

Write

↓

Load

- Human Writing
- Reader Psychology
- CTA Psychology
- Copywriting
- Threads Best Practices
- Blacklist
- AI Personality

---

Scout

↓

Load

- Threads Best Practices
- Platform Behaviour
- Blacklist
- AI Personality

---

Stats

↓

Load

- Threads Best Practices
- Platform Behaviour
- AI Personality

Knowledge loading should remain dynamic.

Unused knowledge should never participate in reasoning.

---

# Brain Selection

After loading the required context,

System Brain selects the appropriate specialised brain.

```
Write

↓

HERO Brain
```

```
Scout

↓

Scout Brain
```

```
Stats

↓

Stats Brain
```

```
Planner

↓

Planner Brain
```

Only one brain should become the Primary Brain for each request.

Additional brains may participate only when collaboration is required.

---

# Multi-Brain Collaboration

Certain requests require more than one specialised brain.

Example:

```
Write Request

↓

HERO Brain

↓

AURA Validation
```

---

```
Scout Request

↓

Scout Brain

↓

AURA Validation
```

---

```
Stats Request

↓

Stats Brain
```

Collaboration should remain minimal.

Each specialised brain should perform only its own responsibility.

System Brain remains responsible for coordination.

---

# Execution Context

Before execution begins,

System Brain combines every required resource into one Execution Context.

Execution Context includes:

- Active Account Context
- Request Context
- Knowledge Context
- Selected Brain
- Feature Settings

The Execution Context becomes the only input passed to the selected specialised brain.

No specialised brain should independently load additional resources.

---

# Request Preparation

Every request should be fully prepared before execution.

Preparation includes:

- Validating required inputs.
- Resolving missing optional settings.
- Applying saved creator preferences.
- Loading remembered defaults.
- Building the Execution Context.

Once preparation is complete,

System Brain transfers full responsibility to the selected specialised brain.

System Brain does not interfere again until execution has finished.



---

# Execution Flow

Once the Execution Context has been prepared,

System Brain transfers the request to the selected specialised brain.

```
Execution Context

↓

Primary Brain

↓

Execution Result

↓

AURA

↓

Approved Result

↓

Creator
```

System Brain does not participate during reasoning.

It waits until execution has completed.

---

# Response Pipeline

Every AI-generated response follows the same pipeline.

```
Creator Request

↓

System Brain

↓

Primary Brain

↓

AURA Validation

↓

Creator Response
```

No AI-generated output should bypass AURA.

Validation is mandatory whenever content or replies are generated.

---

# Failure Handling

If execution cannot continue,

System Brain should stop immediately.

Possible failure conditions include:

- No Active Account.
- Missing required input.
- Unsupported feature.
- Required knowledge unavailable.
- Primary Brain unavailable.

System Brain should never continue with incomplete execution context.

---

# Retry Logic

Retry should occur only when the failure is recoverable.

Examples include:

- Temporary generation failure.
- Validation failure.
- Response formatting issue.

Retry should never occur when required information is missing.

Example:

Missing Topic

↓

Stop

↓

Request creator input

Not Retry.

---

# Validation Routing

Every completed execution must determine whether validation is required.

```
Execution Complete

↓

Requires Validation?

↓

Yes

↓

AURA

↓

Creator
```

```
Execution Complete

↓

Requires Validation?

↓

No

↓

Creator
```

Examples requiring validation:

- Thread generation.
- Reply generation.

Examples not requiring validation:

- Calendar retrieval.
- Profile settings.
- Dashboard data.
- Statistics retrieval.

---

# Output Rules

System Brain returns only one final response.

Creators should never receive:

- Internal reasoning.
- Knowledge loading.
- Decision process.
- Intermediate outputs.
- Multiple unfinished results.

Only validated, creator-ready output should leave System Brain.

Internal execution remains invisible.



---

# Request Classification

Before execution begins,

System Brain classifies every incoming request.

Two request types exist.

---

## AI Request

Requests requiring reasoning.

Examples include:

- Generate Threads.
- Discover Scout opportunities.
- Generate Scout replies.
- Analyse performance.

AI Requests require:

- Active Account Context.
- Knowledge Context.
- Specialised Brain.
- AURA Validation (when applicable).

---

## System Request

Requests requiring system operations only.

Examples include:

- Open Planner.
- Retrieve Calendar.
- Load Dashboard.
- Retrieve Profile.
- Update Settings.

System Requests bypass AI reasoning completely.

Only the required application data should be retrieved.

The objective is minimising unnecessary AI execution while improving performance.

---

# Priority Rules

System Brain resolves every request using the following priority.

```
Receive Request

↓

Classify Request

↓

Load Active Account

↓

Load Required Knowledge

↓

Select Brain

↓

Execute

↓

Validate (If Required)

↓

Return
```

No stage should be skipped.

No specialised brain should execute before the request has been fully prepared.

---

# Conflict Resolution

If multiple specialised brains could potentially execute a request,

System Brain should:

- Select one Primary Brain.
- Assign supporting brains only when required.
- Prevent duplicate responsibilities.

Every request should have only one decision owner.

Responsibilities should never overlap.

---

# Memory Handling

System Brain does not permanently remember creator interactions.

Persistent information belongs to:

- Active Account Context.
- Historical Performance.
- Application Database.
- Creator Preferences.

System Brain retrieves memory when needed.

It never stores memory independently.

---

# Scalability

System Brain should remain platform-independent.

Adding new platforms or specialised brains should not require redesigning the decision pipeline.

Future expansion should involve:

- Registering a new feature.
- Registering a new specialised brain.
- Registering new platform knowledge.

The core execution pipeline should remain unchanged.

---

# Engine Principle

System Brain is Aura AI's operating system.

It does not create.

It does not analyse.

It does not validate.

Its responsibility is making sure the right brain receives the right context at the right time.

Every request should follow the same philosophy.

Think first.

Prepare completely.

Execute once.

Return confidently.

---

# Final Statement

System Brain exists to make every specialised brain simpler.

Rather than allowing each brain to manage accounts, knowledge, routing, and execution independently,

System Brain centralises those responsibilities into one consistent workflow.

This separation allows every specialised brain to focus on only one responsibility.

As Aura AI grows,

System Brain remains stable.

New capabilities should be added by extending specialised brains and knowledge,

not by increasing the complexity of the operating system.