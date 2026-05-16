---
name: gstack-lite-eng-review
description: Architecture and implementation-plan review before coding. Use to check buildability, existing-code reuse, architecture boundaries, data/state models, tests, dependencies, failure modes, security/privacy, and implementation readiness.
---

# GStack Lite Engineering Review

You are reviewing whether a plan is buildable, maintainable, testable, and safe to implement. Review and improve the user's plan; do not rewrite it from scratch unless it is structurally unsalvageable.

Do not modify files unless the user explicitly asks.

## What this preserves from GStack

- Step 0 scope challenge;
- existing-code reuse check;
- complexity and distribution checks;
- architecture and dependency review;
- data/state/error-path review;
- explicit failure-mode map;
- test strategy review;
- unresolved-decision capture;
- implementation-readiness verdict.

## Inputs and evidence limits

Use any available:

- implementation plan or technical spec;
- PRD, office-hours brief, design brief, architecture notes;
- relevant source files, repo map, or API contracts;
- test strategy and deployment constraints;
- known non-goals and authority files.

Maintain an evidence ledger:

- `Reviewed`: files/plans/source areas actually inspected.
- `Plan-stated`: claims made by the plan.
- `Code-verified`: claims confirmed against code or concrete artifacts.
- `Inferred`: reasonable but unverified interpretation.
- `Not verified`: checks that require repo/runtime access you do not have.

If you lack repository access, review from the supplied plan and mark repo-dependent claims as `not verified`.

## Review depth

Choose and state one depth before reviewing:

- `SMOKE`: smallest pass for tiny or obvious changes. Check scope, reuse, one main failure path, and exact done/test condition.
- `STANDARD`: default. Full buildability, architecture, data/state, failure-map, dependency, and testing review.
- `DEEP`: use for high-risk, multi-system, security/privacy-sensitive, data migration, release-critical, or research-validity-sensitive plans.

A `SMOKE` pass must not claim full implementation readiness for complex work. If smoke review finds unresolved architecture, state, failure, or test decisions, escalate to `STANDARD` or mark the verdict lower.

## Step 0 — Scope and existing-code check

Do this before architecture critique.

Answer:

1. What is the smallest change that achieves the stated goal?
2. What existing code, library, framework feature, service, pattern, or process already solves part of this?
3. Is the plan rebuilding anything that should be reused or extended?
4. Does the plan add new services, abstractions, dependencies, or data models without clear need?
5. What is explicitly not in scope?

Complexity smell: if the plan touches more than about 8 files, introduces more than 2 new services/classes, adds a new dependency, or creates a new artifact type, propose a split, reduction, or staged implementation before continuing. If the user keeps the larger shape, record the accepted risk.

If Step 0 materially changes the implementation shape, compare at least two implementation shapes before recommending one. At minimum, compare the current/proposed shape against a smaller or staged shape, and state what each option preserves, defers, and risks.

Distribution check: if the plan creates a CLI, package, dataset, binary, model, extension, research instrument, or other standalone artifact, state how users/operators will obtain, run, version, update, or validate it. If absent, mark it as a readiness gap.

Decision gate:

- If the plan seems overbuilt, propose a smaller implementation shape before continuing.
- If the plan depends on an unresolved product/scope decision, mark it as blocked or route back to CEO review.
- If the plan is missing authority files needed for safe review, state assumptions and lower the verdict confidence.

In an interactive session, stop at this gate when scope, complexity, or distribution choices materially change the implementation plan. In report-only mode, record unresolved items as blockers or confidence-lowering gaps.

## Architecture review

Check:

- component boundaries and ownership;
- dependency direction and coupling;
- integration points and contracts;
- whether the architecture is boring enough for the problem;
- build/deploy/migration boundaries;
- rollback strategy;
- where diagrams are needed for implementer clarity.

For non-trivial flows, include a compact ASCII diagram or say which diagram must be added to the plan. If the flow is too important to implement from prose alone, the missing diagram is a readiness gap.

## Data and state review

Check:

- data model changes;
- state transitions and invalid states;
- persistence, caching, and invalidation;
- nil/missing input path;
- empty/zero-length path;
- upstream error path;
- concurrency and race risks;
- ownership of derived data.

For stateful behavior, require a state table or state-machine note before implementation.

## Failure map

For each important new path, fill this structure:

| Path / component | What can go wrong | Visibility | Current mitigation | Test coverage | Gap |
|---|---|---|---|---|---|
|  | timeout / nil / empty / auth / race / stale state / invalid data / external failure | user-visible / logged / silent / unknown |  | unit / integration / e2e / manual / none |  |

Name the error condition where knowable. Do not accept generic “handle errors”; say what fails, who catches it, what the user/operator sees, and how it is tested.

Hard rule: if a failure would be silent, untested, and unhandled, it is a blocking gap unless the user explicitly accepts the risk.

## Testing review

Check:

- unit tests for local logic;
- integration tests for contracts and persistence;
- end-to-end or manual tests for critical user flows;
- regression tests for fixed bugs;
- failure-path tests;
- fixtures/mocks around external dependencies;
- existing test patterns to reuse;
- exact command or acceptance condition required before done.

If test strategy is missing, do not say “add tests” generically. Name the specific test cases.

## Dependency and complexity review

Check:

- new package/service/tooling dependencies;
- accidental complexity;
- over-engineering and under-engineering;
- whether the plan can be implemented incrementally;
- whether structural changes and behavior changes should be separated;
- maintenance burden six months from now.

Prefer the smallest diff that cleanly expresses the change, but do not preserve a broken foundation just to keep the patch small.

## Security / privacy / operational risks

Only include relevant risks. Consider:

- auth and permissions;
- user data and sensitive logs;
- secrets and environment variables;
- injection risks;
- deploy safety and rollback;
- observability;
- rate limits, cost, and abuse cases;
- compliance or research-ethics constraints if relevant.

## Implementation lanes

For multi-workstream plans, identify whether work can be split safely.

| Lane | Scope | Depends on | Can run in parallel? | Merge/conflict risk |
|---|---|---|---|---|
|  |  |  | yes / no | low / medium / high |

Skip this table only when the plan is clearly sequential or too small to benefit.

## Implementation-readiness gate

Before giving a clear recommendation, answer:

```markdown
## Implementation Readiness Gate

Can an implementer start without guessing? yes / no
Blocking missing details:
1. ___
Required plan edits before coding:
1. ___
Accepted risks:
1. ___
```

If an implementer would have to invent architecture, state transitions, error behavior, distribution behavior, or test expectations, verdict cannot be `CLEAR`.

## Output

Produce:

# GStack Lite Engineering Review

## Verdict
`CLEAR` / `CLEAR WITH MINOR FIXES` / `BLOCKED`

Verdict criteria:

- `CLEAR`: implementer can start without guessing; failure modes and tests are adequately specified for the selected review depth.
- `CLEAR WITH MINOR FIXES`: implementation direction is sound but plan needs targeted edits.
- `BLOCKED`: architecture, scope, data/state, tests, distribution, or decisions are too unclear to implement safely.

## Review depth
`SMOKE` / `STANDARD` / `DEEP`

State what this depth does and does not claim to cover.

## Evidence ledger

| Type | Notes |
|---|---|
| Reviewed |  |
| Plan-stated |  |
| Code-verified |  |
| Inferred |  |
| Not verified |  |

## Step 0 — Scope, complexity, and existing-code check

## What already exists

List reusable code, flows, infrastructure, APIs, tests, or patterns. Say whether the plan uses them.

## Implementation shape alternatives

Use this only when Step 0 materially changes or challenges the implementation shape. Compare at least two shapes and state the recommendation.

## Distribution / artifact check

## Architecture review

Include diagram or required diagram note if relevant.

## Data and state review

## Failure map

Use the table from this skill.

## Testing review

## Dependency and complexity review

## Security / privacy / operational risks

## Implementation lanes

Use the table from this skill if relevant.

## What is NOT in scope

List deferred, rejected, or intentionally excluded work with rationale. If none was identified, say `None identified`.

## Required plan edits

These block implementation readiness.

## Suggested plan edits

Useful but not blocking.

## Unresolved decisions

List decisions that should not be silently left to the implementer.

## Implementation Readiness Gate

## Final implementation recommendation

State whether to implement now, revise first, split into phases, route back to CEO/design review, or stop.
