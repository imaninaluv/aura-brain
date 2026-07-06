# System Brain

Version: 1.0
Status: Locked
Last Updated: 2026-07-06

---

# Identity

System Brain is Aura AI's operating system.

It coordinates every request throughout Aura AI.

System Brain never generates content.

System Brain never analyses performance.

System Brain never validates outputs.

Its only responsibility is coordinating execution.

---

# Responsibility

System Brain is responsible for:

- Receiving every creator request.
- Identifying creator intent.
- Selecting the requested feature.
- Classifying the request.
- Building the Execution Context.
- Selecting the Primary Brain.
- Coordinating execution.
- Routing outputs to AURA when validation is required.
- Returning the final response.

System Brain should never perform responsibilities belonging to specialised brains.

---

# Core Principle

Every request follows the same operating principle.

```
Receive

↓

Understand

↓

Prepare

↓

Execute

↓

Validate

↓

Return
```

Preparation always happens before execution.

Execution always happens before validation.

Validation always happens before returning a response.

---

# Thinking Pipeline

Every creator request enters the same thinking pipeline.

```
Creator Request

↓

Identify Intent

↓

Identify Feature

↓

Classify Request

↓

Load Active Account

↓

Build Execution Context

↓

Aura Brain

↓

Knowledge Context

↓

Select Primary Brain

↓

Execute
```

Only after execution has completed does the request continue to validation.

---

# Intent Detection

The first decision is identifying the creator's intent.

Examples include:

- Write Content
- Scout Conversations
- Analyse Performance
- Open Home
- Open Planner
- View Stats
- Update Profile

Unknown intent should never proceed beyond this stage.

Unknown requests should return a clarification request rather than continuing execution.

---

# Feature Selection

After identifying intent,

System Brain selects the corresponding application feature.

Examples include:

Write

↓

Write Feature

---

Scout

↓

Scout Feature

---

Stats

↓

Stats Feature

---

Planner

↓

Planner Feature

---

Profile

↓

Profile Feature

Feature selection should remain independent from specialised brain selection.

Creators request features.

System Brain decides which brain executes them.


---

# Request Classification

After selecting the requested feature,

System Brain classifies the request.

Two request types exist.

---

## AI Request

AI Requests require reasoning.

Examples include:

- Generate Threads
- Discover Scout Opportunities
- Generate Scout Replies
- Analyse Performance

AI Requests continue through the complete AI execution pipeline.

---

## System Request

System Requests require application logic only.

Examples include:

- Open Home
- Open Planner
- Retrieve Calendar
- Load Dashboard
- Retrieve Profile
- Update Settings

System Requests bypass specialised reasoning completely.

Only the required application data should be retrieved.

The objective is minimising unnecessary AI execution.

---

# Active Account Loading

Every request begins by loading the Active Account.

```
INPUT

↓

Creator Request

↓

PROCESS

Load Active Account

↓

OUTPUT

Active Account Context
```

The Active Account Context should contain:

- Account Identity
- Account Type
- Connected Platform
- Creator Preferences
- Account History

No execution should begin before the Active Account Context has been successfully prepared.

---

# Execution Context

System Brain builds one Execution Context for every request.

Execution Context represents everything required for execution.

```
Execution Context

├── Request Context
├── Active Account Context
├── Feature Context
└── Creator Preferences
```

Execution Context becomes the primary input for Aura Brain.

No specialised brain should build its own execution context.

---

# Knowledge Loading

System Brain never decides which knowledge documents should be used.

That responsibility belongs entirely to Aura Brain.

```
Execution Context

↓

Aura Brain

↓

Knowledge Selection

↓

Knowledge Context
```

Knowledge selection should be determined dynamically using:

- Selected Feature
- Active Platform
- Active Account
- Creator Preferences

Only the knowledge required for the current request should be loaded.

Unused knowledge should never participate in reasoning.

---

# Brain Selection

Once the Knowledge Context has been prepared,

System Brain selects the Primary Brain.

```
Execution Context

+

Knowledge Context

↓

Select Primary Brain

↓

Execute
```

Only one Primary Brain may own a request.

Supporting brains may participate only when required.

System Brain always remains responsible for coordination.

---

# Collaboration Rules

Collaboration should remain minimal.

Each specialised brain performs only one responsibility.

Examples include:

```
HERO

↓

AURA
```

```
Scout Brain

↓

AURA
```

```
Stats Brain

↓

Return
```

System Brain coordinates every collaboration.

No specialised brain should directly invoke another specialised brain.



---

# Execution Rules

Once the Primary Brain has been selected,

System Brain transfers ownership of the request.

```
Execution Context

↓

Knowledge Context

↓

Primary Brain

↓

Execution Result
```

During execution,

System Brain does not participate in reasoning.

Its responsibility is waiting for the execution result.

---

# Validation Routing

After execution,

System Brain determines whether validation is required.

```
Execution Result

↓

Validation Required?

↓

Yes

↓

AURA

↓

Approved Result
```

```
Execution Result

↓

Validation Required?

↓

No

↓

Approved Result
```

Validation should only occur when AI-generated content requires quality review.

Examples include:

- Thread Generation
- Scout Reply Generation

Examples that do not require validation include:

- Dashboard Retrieval
- Calendar Retrieval
- Profile Retrieval
- Settings Update

---

# Response Pipeline

Every request follows the same response pipeline.

```
Creator Request

↓

System Brain

↓

Aura Brain

↓

Primary Brain

↓

AURA (If Required)

↓

Creator Response
```

Every creator response should originate from one completed execution.

Partial responses should never be returned.

---

# Failure Handling

Execution should stop immediately whenever a critical dependency is unavailable.

Examples include:

- Active Account unavailable.
- Execution Context incomplete.
- Primary Brain unavailable.
- Invalid creator request.

When execution stops,

System Brain should return a recoverable response whenever possible.

The creator should receive guidance instead of an unexpected failure.

---

# Retry Rules

Retry should occur only when the failure is temporary.

Examples include:

- Temporary generation failure.
- Temporary validation failure.
- Temporary formatting issue.

Retry should never occur when creator input is missing.

Example:

```
Topic Missing

↓

Stop Execution

↓

Request Creator Input
```

Retries should remain limited.

Repeated failures should be returned to the creator with an appropriate explanation.

---

# Output Rules

System Brain returns only one creator-ready response.

The creator should never receive:

- Internal reasoning.
- Execution Context.
- Knowledge Context.
- Brain selection.
- Validation process.
- Intermediate outputs.

Every response leaving System Brain should be complete, validated when required, and ready for immediate use.



---

# Conflict Resolution

Only one Primary Brain may own a request.

If multiple specialised brains could potentially execute the same request,

System Brain should:

- Select one Primary Brain.
- Assign supporting brains only when required.
- Prevent overlapping responsibilities.

Every request should have one decision owner.

Execution ownership should never be shared.

---

# Memory Handling

System Brain does not permanently store creator memory.

Persistent information belongs to:

- Active Account
- Account History
- Creator Preferences
- Application Database

System Brain retrieves only the information required for the current execution.

Memory retrieval should always remain contextual.

No specialised brain should independently manage persistent memory.

---

# Scalability

System Brain should remain platform-independent.

Adding new platforms, features, or specialised brains should never require redesigning the operating system.

Future expansion should involve:

- Registering a new feature.
- Registering a new specialised brain.
- Registering new platform knowledge.

The execution pipeline should remain unchanged.

---

# Engine Principle

System Brain is Aura AI's operating system.

It does not create.

It does not analyse.

It does not validate.

Its responsibility is ensuring that every request reaches the correct specialised brain with the correct execution context.

System Brain prepares.

Aura Brain provides knowledge.

Specialised Brains reason.

AURA validates.

Every request should follow the same philosophy.

Prepare completely.

Execute once.

Return confidently.

---

# Final Statement

System Brain exists to simplify every other specialised brain.

Rather than allowing each brain to independently manage routing, context, execution, and memory,

System Brain centralises those responsibilities into one consistent workflow.

Each specialised brain should focus on only one responsibility.

As Aura AI evolves,

new capabilities should be added by extending specialised brains and knowledge,

not by increasing the complexity of the operating system.

A stable operating system allows Aura AI to grow without becoming more complicated.
