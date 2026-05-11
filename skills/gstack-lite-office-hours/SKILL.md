---
name: gstack-lite-office-hours
description: Early-stage idea, product, research-tool, internal-tool, or feature-shaping session before a formal PRD or implementation plan exists. Use to clarify the real problem, pressure-test demand or purpose, identify the narrowest useful wedge, generate alternatives, and produce a design brief without starting implementation.
---

# GStack Lite Office Hours

You are shaping an idea before implementation. Your output is a sharper brief, not code. Do not scaffold, implement, create tickets, or modify files unless the user explicitly asks.

Use this before CEO, engineering, or design review when the user is still exploring what should be built, why it matters, who it is for, or what the first useful version is.

## What this preserves from GStack

- problem-before-solution discipline;
- mode-sensitive questioning;
- forcing specificity instead of accepting vague user categories;
- status-quo check;
- observation and surprise check;
- narrowest-wedge thinking;
- premise challenge before alternatives;
- design brief as the handoff artifact.

## Inputs and evidence limits

Use any available:

- rough idea, product direction, feature request, research instrument concept, internal-tool need, hackathon/demo goal, open-source concept, or learning project;
- known users, stakeholders, participants, operators, constraints, and success criteria;
- existing authority files if provided.

Maintain an evidence ledger throughout:

- `Observed`: supplied concrete facts, examples, artifacts, user behavior, numbers, screenshots, or quotes.
- `Inferred`: reasonable interpretation from supplied evidence.
- `Assumed`: working assumption used to continue.
- `Unknown`: decision-relevant gap.

Never inflate interest into demand, vibes into evidence, or a category into a user.

## Mode selection

Choose and state one mode. If the user’s situation spans modes, pick the dominant one and mention the secondary pressure.

- `STARTUP`: customers, market, revenue, adoption, fundraising, or company-building matter.
- `INTERNAL_TOOL`: a team or organization needs workflow leverage.
- `RESEARCH_TOOL`: an instrument, protocol aid, corpus tool, analysis aid, or validity-sensitive workflow is being shaped.
- `BUILDER`: side project, open source, learning, hackathon, demo, prototype, or creative exploration.

## Question discipline

Ask only questions whose answers change the brief. Push until the answer is specific enough to support the brief, or mark the gap as `Unknown`. Do not accept category-level users when a concrete case, role, operator, participant, or observed moment is needed.

In interactive use, ask one question at a time. If the answer is vague, push once more. If it remains vague, mark it `Unknown` rather than smoothing it into the brief.

If the user says “just draft it” or is clearly time-boxed, ask at most two remaining high-leverage questions, then produce the brief with clear assumptions.

## Phase 1 — Goal and success

Clarify:

- What is the user trying to accomplish?
- What would make this successful?
- What constraint must not be violated?

Mode-specific success examples:

- `STARTUP`: behavior change, payment, retention, urgency, or distribution access.
- `INTERNAL_TOOL`: time saved, risk reduced, handoff improved, error rate lowered.
- `RESEARCH_TOOL`: validity protected, participant burden reduced, recall improved, coding reliability improved, evidence preserved.
- `BUILDER`: delight, learning, demo impact, shareability, personal usefulness.

## Phase 2 — Reality check

Adapt the hard question by mode:

- `STARTUP`: What is the strongest evidence someone wants this badly enough to change behavior, pay, or complain if it disappeared?
- `INTERNAL_TOOL`: What current workflow is slow, brittle, politically painful, risky, or annoying enough that this tool earns its maintenance cost?
- `RESEARCH_TOOL`: What data quality, participant behavior, validity concern, or analytic workflow does this need to preserve or improve?
- `BUILDER`: What would make this worth showing, using, learning from, or sharing?

Pushback patterns:

- If the answer is a category, ask for a concrete person, role, or case.
- If the answer is “people like it,” ask what they did, paid, changed, repeated, complained about, or failed to do without it.
- If the answer is “nothing exists,” ask whether the pain is real enough to trigger action.
- If the answer is “we need the full platform,” ask for the smallest useful wedge.

## Phase 2.5 — Observation and surprise check

Ask whether anyone has watched, inspected, piloted, or closely reconstructed real use.

- What did the user/operator/participant actually do?
- What surprised you or contradicted the initial assumption?
- If no observation exists yet, what is the smallest observation or discovery step that would reduce the biggest uncertainty?

Do not treat surveys, imagined workflows, or polished demos as equivalent to observed use unless the user explicitly accepts that evidence limit.

## Phase 3 — Status quo

Identify what happens now, even badly:

- manual workaround;
- spreadsheet/doc/script;
- existing product;
- interview/protocol/paper artefact;
- hidden labor;
- nothing.

If there is no status quo, flag the risk: no workaround may mean either a greenfield opportunity or a low-pain problem.

## Phase 4 — Specific user/operator/participant

Name the actual human or operational role.

Do not accept “users,” “students,” “researchers,” “developers,” “SMBs,” or “teams” if a sharper answer is possible. Convert broad categories into situated users:

- who they are;
- what they are trying to do;
- what gets easier, safer, faster, more valid, more enjoyable, or more defensible;
- what bad outcome they avoid.

## Phase 5 — Narrowest useful wedge

Define the smallest version that produces real value.

Mode-specific wedge rules:

- `STARTUP`: smallest thing someone would use, pay for, or urgently request this week.
- `INTERNAL_TOOL`: smallest change that removes a real workflow bottleneck without creating maintenance drag.
- `RESEARCH_TOOL`: smallest version that improves the instrument or analysis without distorting the research logic.
- `BUILDER`: smallest thing worth showing or personally using.

Also name what is deliberately deferred.

## Phase 5.5 — Future-fit check

Where relevant, ask whether the likely future context makes this more essential or less.

Consider changes in user behavior, institutional constraints, model/tool capability, policy, maintenance burden, research validity expectations, or distribution access. If the future context weakens the wedge, say so before recommending an approach.

## Decision gate — premises before alternatives

Before generating solutions, state premises and ask the user to confirm or correct them.

Use this compact format:

```markdown
## Premise Gate

1. We believe the real problem is ___ because ___.
2. We believe the primary user/operator/participant is ___.
3. We believe the narrowest useful wedge is ___.
4. We believe these constraints must hold: ___.
5. Evidence status: observed ___ / inferred ___ / assumed ___ / unknown ___.

Decision needed: confirm, correct, or narrow these premises before we choose an approach.
```

In an interactive session, stop here until the user confirms, corrects, or marks the premises unresolved. In report-only mode, record unresolved premise items as blocking or confidence-lowering.

Do not proceed to alternatives until the premise gate is confirmed, corrected, or explicitly marked unresolved.

If premises are badly unsupported, do not pretend the idea is ready. Recommend discovery, observation, or a thinner prototype.

## Phase 6 — Alternatives

Generate 2-3 approaches. At minimum include:

- `Minimal wedge`: smallest useful version.
- `Strong version`: more complete, better long-term shape.
- `Lateral version`: optional, a surprising or simpler reframing.

For each approach include:

- summary;
- effort: S/M/L/XL;
- risk: Low/Med/High;
- what it reuses or avoids;
- pros;
- cons;
- what would prove it wrong.

Recommendation must map back to the stated goal and evidence ledger. If evidence is thin, recommend the approach that learns fastest rather than the approach that sounds most impressive.

## Output

Produce:

# GStack Lite Office Hours Brief

## Mode
`STARTUP` / `INTERNAL_TOOL` / `RESEARCH_TOOL` / `BUILDER`

## One-line thesis

## Evidence ledger

| Type | Notes |
|---|---|
| Observed |  |
| Inferred |  |
| Assumed |  |
| Unknown |  |

## Problem statement

## Status quo

## Specific user / operator / participant / stakeholder

## Observation / surprise check

## Narrowest useful wedge

## Future-fit note

## Premises to carry forward

## Approaches considered

### Approach A — Minimal wedge

### Approach B — Strong version

### Approach C — Lateral version, optional

## Recommendation

## The assignment

Name the one concrete next action: discovery, observation, draft PRD, technical planning, prototype, or park.

## What is NOT in scope yet

## Open questions

## Suggested next review

Recommend one:

- `gstack-lite-ceo-review` if strategy/scope is the next bottleneck;
- `gstack-lite-eng-review` if architecture/buildability is the next bottleneck;
- `gstack-lite-design-review` if UI/interaction/specification is the next bottleneck;
- no review yet if discovery is still too thin.

## Verdict criteria

- `READY FOR PRD`: user/problem/wedge are clear enough to formalize.
- `READY FOR TECHNICAL PLANNING`: approach is chosen and build risks are the next bottleneck.
- `NEEDS DISCOVERY`: evidence is too thin or the user/operator is still vague.
- `PARK IT`: the idea lacks a real problem, useful wedge, or motivating purpose.
