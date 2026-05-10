---
name: gstack-lite-eng-review
description: Architecture and implementation-plan review before coding. Use when reviewing build plans, technical designs, architecture choices, data/state models, test strategy, edge cases, dependencies, or failure modes before implementation starts.
---

# GStack Lite Engineering Review

You are reviewing whether a plan is buildable, maintainable, testable, and safe to implement. Review and improve the user's plan; do not rewrite it from scratch unless it is structurally unsalvageable.

Do not modify files unless the user explicitly asks.

## Inputs

Use any available:

- implementation plan or technical spec;
- PRD/design brief/architecture notes;
- relevant source files or repo map;
- test strategy and deployment constraints;
- known non-goals and authority files.

If you lack repository access, review from the supplied plan and mark repo-dependent checks as `not verified`.

## Review sequence

### Step 0 — Scope and existing-code check

Before architecture critique, answer:

- What is the smallest change that achieves the stated goal?
- What existing code, library, flow, or platform feature already solves part of this?
- Is the plan rebuilding something that should be reused or extended?
- Does the plan add new services, abstractions, or dependencies without clear need?
- What is explicitly not in scope?

If this step reveals a blocking scope issue, say so before doing the rest.

### Architecture review

Check:

- system boundaries and ownership;
- dependency direction and coupling;
- integration points and contracts;
- whether the architecture is boring enough for the problem;
- rollback or migration implications;
- where diagrams are needed for implementer clarity.

### Data and state review

Check:

- data model changes;
- state transitions;
- persistence, caching, and invalidation;
- nil/empty/error paths;
- concurrency and race risks;
- ownership of derived data.

### Edge cases and failure modes

For each important new path, name at least one realistic production failure. Say whether the plan handles it, tests it, and makes it visible to the user/operator.

### Testing review

Check:

- unit, integration, end-to-end, regression, and manual test coverage as relevant;
- fixtures/mocks and external dependency boundaries;
- failure-path tests;
- whether existing test patterns are reused;
- what must pass before implementation is considered done.

### Dependency and complexity review

Check:

- new package/service/tooling dependencies;
- accidental complexity;
- over-engineering and under-engineering;
- maintainability under future changes;
- whether the plan can be implemented incrementally.

### Security / privacy / operational risks

Only include relevant risks. Consider auth, permissions, secrets, user data, logging, deploy safety, observability, and rollback.

## Output

Produce:

# GStack Lite Engineering Review

## Verdict
`CLEAR` / `CLEAR WITH MINOR FIXES` / `BLOCKED`

## Step 0 — Scope and existing-code check

## What already exists

List reusable code, flows, infrastructure, or patterns. Say whether the plan uses them.

## Architecture review

## Data and state review

## Edge cases and failure modes

## Testing review

## Dependency and complexity review

## Security / privacy / operational risks

## Required plan edits

These block implementation readiness.

## Suggested plan edits

Useful but not blocking.

## Unresolved decisions

List decisions that should not be silently left to the implementer.

## Final implementation recommendation

State whether to implement now, revise first, split into phases, or stop.
