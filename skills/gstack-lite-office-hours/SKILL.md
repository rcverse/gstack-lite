---
name: gstack-lite-office-hours
description: Early-stage idea, product, research-tool, internal-tool, or feature-shaping session before a formal PRD or implementation plan exists. Use to clarify the problem, pressure-test demand or purpose, identify the narrowest useful wedge, generate alternatives, and produce a design brief.
---

# GStack Lite Office Hours

You are helping shape an idea before implementation. The output is a sharper brief, not code. Do not scaffold, implement, or modify files unless the user explicitly asks.

Use this before CEO, engineering, or design review when the user is still exploring what should be built, why it matters, or what the first useful version is.

## Inputs

Use any available:

- rough idea, feature request, research instrument concept, product direction, internal-tool need, hackathon/demo goal, or open-source concept;
- known users, stakeholders, constraints, and success criteria;
- existing project authority files if provided.

If the user has already supplied a full PRD or implementation plan, do not re-interrogate everything. Run a compressed premise and alternatives pass.

## Mode selection

Choose and state one mode:

- `STARTUP` — user is considering customers, market, revenue, adoption, or company-building.
- `INTERNAL_TOOL` — user needs a useful tool inside an organization or workflow.
- `RESEARCH_TOOL` — user needs an instrument, protocol aid, corpus tool, or analysis support.
- `BUILDER` — side project, open source, learning, demo, prototype, or creative exploration.

The questioning style changes by mode, but the core goal stays the same: sharpen the real problem and first useful wedge.

## Conversation sequence

Ask only the questions that are still unknown. Do not turn this into a form.

### 1. Goal and context

Clarify what the user is trying to accomplish and what would count as success.

### 2. Reality check

Adapt by mode:

- `STARTUP`: What evidence shows someone wants this badly enough to change behavior, pay, or complain if it disappeared?
- `INTERNAL_TOOL`: What current workflow is slow, brittle, risky, or annoying enough that this tool earns its maintenance cost?
- `RESEARCH_TOOL`: What data, participant behavior, validity concern, or analytic workflow does this instrument need to preserve?
- `BUILDER`: What would make this worth showing, using, learning from, or sharing?

### 3. Status quo

What are people doing now, even badly? Spreadsheets, manual steps, existing apps, scripts, interviews, paper protocols, or nothing. If the answer is "nothing," ask whether the pain is real enough.

### 4. Specific user or operator

Name the concrete person, role, participant, researcher, maintainer, or operator. Avoid category-level answers when a real user can be named.

### 5. Narrowest useful wedge

Find the smallest version that produces real value quickly. For research tools, this means the smallest version that improves the instrument without damaging validity. For internal tools, it means the smallest version that removes real workflow pain. For startups, it means the smallest version someone would actually use or pay for.

### 6. Premise challenge

State the core premises clearly:

- We believe X problem matters because Y evidence.
- We believe this user/operator needs Z outcome.
- We believe the first useful wedge is W.
- We believe these constraints must not be violated.

Ask the user to confirm or correct the premises before moving on.

### 7. Alternatives

Generate 2-3 approaches:

- minimal viable wedge;
- stronger/ideal version;
- lateral or surprising version if useful.

For each:

- Summary;
- Effort: S/M/L/XL;
- Risk: Low/Med/High;
- Pros;
- Cons;
- What it reuses or avoids.

Recommend one, but do not pretend uncertainty is resolved if evidence is missing.

## Output

Produce:

# GStack Lite Office Hours Brief

## Mode
`STARTUP` / `INTERNAL_TOOL` / `RESEARCH_TOOL` / `BUILDER`

## One-line thesis

## Problem statement

## Evidence / reality check

Say what is known, assumed, and still unverified.

## Status quo

## Specific user / operator / participant / stakeholder

## Narrowest useful wedge

## Premises to carry forward

## Approaches considered

### Approach A — name

### Approach B — name

### Approach C — name, optional

## Recommendation

## What is NOT in scope yet

## Open questions

## Suggested next review

Recommend one:

- `gstack-lite-ceo-review` if scope/strategy is the next bottleneck;
- `gstack-lite-eng-review` if architecture/buildability is the next bottleneck;
- `gstack-lite-design-review` if UI/interaction/specification is the next bottleneck;
- no review yet if discovery is still too thin.
