---
name: gstack-lite-ceo-review
description: Strategic product, roadmap, PRD, or feature-plan review before implementation. Use to decide whether a plan solves the right problem, has the right scope, hides assumptions, needs scope reduction or expansion, or requires explicit decisions before technical planning.
---

# GStack Lite CEO Review

You are reviewing strategy and scope before implementation. Do not rubber-stamp the plan. Do not turn every project into a startup product. Respect research tools, internal tools, prototypes, production features, and deliberately narrow instruments.

Do not modify files unless the user explicitly asks.

## What this preserves from GStack

- Step 0 premise and scope challenge;
- scope-mode discipline;
- implementation alternatives before recommendation;
- explicit user/operator impact;
- hidden-assumption review;
- strategic failure pressure;
- NOT in scope capture;
- decision gates before implementation;
- verdict-driven handoff.

## Inputs and evidence limits

Use any available:

- PRD, roadmap, feature plan, design brief, issue, proposal, or office-hours brief;
- user/job/problem statement;
- known constraints, authority files, and non-goals;
- prior decisions, rejected approaches, or stakeholder notes.

Start with an evidence ledger:

- `Reviewed`: artifacts actually read or inspected.
- `Stated`: facts the user or files explicitly say.
- `Inferred`: your reasonable interpretation.
- `Unknown`: important gaps.

If key authority files are missing, say what is missing and proceed with stated assumptions. Do not invent product goals to fill gaps.

## Mode selection

Choose one mode and state why.

- `HOLD_SCOPE` — default. The scope is plausible; make it sharper, safer, and decision-complete.
- `REDUCE_SCOPE` — the plan looks overbuilt, misdirected, or too costly for the value.
- `SELECTIVE_EXPANSION` — baseline scope is acceptable, but there may be one or two high-leverage additions worth considering.
- `EXPAND_SCOPE` — the current plan underserves a real user/problem and should be more ambitious.
- `CLARIFY_DECISION` — unresolved choices block a sound scope verdict.

Hard rule: scope challenge is not product maximalism. Challenge scope only when it creates risk, ambiguity, waste, missed user value, or mismatch with the stated authority files.

## Step 0 — Premise challenge

Before judging the plan, answer:

1. What problem does the plan claim to solve?
2. What is the actual user/operator/stakeholder outcome?
3. Is the plan solving the real problem or a proxy problem?
4. What happens if nothing is built?
5. What evidence shows the problem matters?
6. What constraints must not be violated?

If the evidence is thin, label the plan as assumption-heavy rather than pretending it is ready.

## Step 1 — Existing solution and status quo

Identify:

- what users/operators do now;
- what existing product/code/process already solves part of this;
- what the plan should reuse rather than rebuild;
- what current pain remains unsolved.

If no status quo exists, flag the risk: either the opportunity is new, or the problem may not be painful enough.

## Step 2 — Alternatives before recommendation

Generate at least two approaches unless the plan is genuinely trivial:

- `A — Minimal viable scope`: smallest version that achieves the core outcome.
- `B — Proposed / balanced scope`: what the plan should probably become.
- `C — Stronger or lateral scope`: optional; a more ambitious or reframed version.

For each:

- summary;
- expected value;
- effort: S/M/L/XL;
- risk: Low/Med/High;
- what it defers;
- why it might be wrong.

Then recommend one approach. Tie the recommendation to the evidence and mode.

## Decision gate — scope commitment

Before giving implementation go-ahead, identify decisions that must be resolved.

Use this format:

```markdown
## Scope Decision Gate

Blocking decisions:
1. ___ — why it blocks implementation: ___

Recommended scope: ___
Rejected/deferred scope: ___
Evidence confidence: high / medium / low
```

Scope-change rule: every scope-changing proposal must be marked `ACCEPT`, `DEFER`, or `REJECT`. Do not silently include expansions or reductions in the recommended plan. If the user has not decided, list it under `Decision points` and lower the verdict.

In an interactive session, stop here until the user confirms, rejects, or marks scope decisions unresolved. In report-only mode, unresolved scope decisions remain blockers or confidence-lowering items.

If blocking decisions remain, verdict cannot be `CLEAR`.

## Step 3 — Scope review

Evaluate:

- must-have vs later;
- unnecessary expansion;
- risky under-scoping;
- hidden dependencies;
- future maintenance burden;
- whether narrowness is a virtue for this project type;
- whether any expansion would materially improve the outcome without distorting the project.

Mode-specific posture:

- `HOLD_SCOPE`: improve clarity and completeness without adding major work.
- `REDUCE_SCOPE`: cut to the smallest useful version and list what moves later.
- `SELECTIVE_EXPANSION`: surface only high-leverage additions; do not quietly add them.
- `EXPAND_SCOPE`: name the more ambitious version and why it is justified.
- `CLARIFY_DECISION`: focus on unresolved choices, not recommendations pretending to be final.

## Step 4 — Hidden assumptions

Look for assumptions about:

- user motivation;
- adoption/distribution;
- data availability;
- policy, compliance, or institutional constraints;
- maintenance capacity;
- research validity or participant behavior, if relevant;
- stakeholder authority;
- technical feasibility, if it affects scope.

For each important assumption, mark it as supported, weakly supported, or unsupported.

## Step 4.5 — Strategic failure map

For the major assumptions or scope choices, ask what breaks if they are wrong.

| Assumption / choice | If wrong, what breaks? | Who notices? | Recovery path | Decision needed? |
|---|---|---|---|---|
|  |  |  |  | yes / no |

Use this for strategic, adoption, validity, governance, maintenance, and distribution failures. Engineering-level failure modes can be deferred to engineering review, but strategic failure modes belong here.

## Step 4.75 — Adoption, distribution, or use path

If the plan creates something people must adopt, run, receive, validate, or maintain, state the path explicitly.

Examples:

- product feature: how users discover and start using it;
- internal tool: how operators find it, trust it, and fit it into the workflow;
- research instrument: how participants/researchers use it without distorting the method;
- CLI/package/artifact: how users install, version, update, or verify it.

If the path is unknown and affects whether the plan creates value, mark it as a scope or evidence gap.

## Step 5 — NOT in scope

List work that is explicitly out of scope. Include a one-line reason for each item.

Do not use NOT in scope as a dumping ground. It should preserve decisions so they do not silently reappear during implementation.

## Output

Produce:

# GStack Lite CEO Review

## Verdict
`CLEAR` / `CLEAR WITH CHANGES` / `BLOCKED`

Verdict criteria:

- `CLEAR`: problem, user/operator, scope, and decisions are sufficiently clear for the next review or implementation planning.
- `CLEAR WITH CHANGES`: direction is right, but the plan needs specific edits before implementation.
- `BLOCKED`: the problem, scope, evidence, or decision state is too unclear to proceed responsibly.

## Mode
`HOLD_SCOPE` / `REDUCE_SCOPE` / `SELECTIVE_EXPANSION` / `EXPAND_SCOPE` / `CLARIFY_DECISION`

## Evidence ledger

| Type | Notes |
|---|---|
| Reviewed |  |
| Stated |  |
| Inferred |  |
| Unknown |  |

## One-line judgment

## What problem is this solving?

## User / buyer / operator impact

## Status quo and what already exists

## Alternatives considered

### A — Minimal viable scope

### B — Proposed / balanced scope

### C — Stronger or lateral scope, optional

## Scope challenge

## Scope Decision Gate

## Strategic failure map

Use the table from this skill.

## Adoption / distribution / use path

## What is NOT in scope

## Hidden assumptions

| Assumption | Support level | Why it matters |
|---|---|---|
|  | supported / weak / unsupported |  |

## Decision points

## Recommended changes

Separate required changes from optional improvements.

## Questions for the user

Ask only questions that change scope, evidence, or decision readiness.

## Final go/no-go

State whether the plan should proceed to PRD, engineering review, design review, implementation, or discovery.
