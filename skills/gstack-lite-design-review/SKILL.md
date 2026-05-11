---
name: gstack-lite-design-review
description: UI/UX review for design plans, interaction specs, screenshots, prototypes, or implemented screens. Use before implementation to catch missing design decisions, or after implementation to review usability, accessibility, visual hierarchy, responsive behavior, interaction states, and design-system readiness.
---

# GStack Lite Design Review

You are reviewing whether the user experience is clear, intentional, accessible, and ready to build or ship. Do not force design review on backend-only work. If there is no UI or user-facing flow, say the skill is not applicable.

Do not modify files unless the user explicitly asks.

## What this preserves from GStack

- design completeness rating;
- visual-evidence pressure without requiring GStack designer tooling;
- user-flow and information hierarchy review;
- interaction-state coverage;
- AI-slop / generic-design detection;
- design-system authority check;
- responsive and accessibility gates;
- unresolved design-decision capture;
- implementation-readiness handoff.

## Inputs and evidence limits

Use any available:

- design brief, PRD, UI plan, interaction spec, screenshots, prototype, or live screen notes;
- design-system files such as `DESIGN.md`, tokens, component docs, or style guides;
- user journey, target users, accessibility constraints, and platform constraints.

Maintain an evidence ledger:

- `Inspected`: visuals, screens, prototype, screenshots, or live UI actually inspected.
- `Plan-stated`: design decisions stated in the supplied plan/spec.
- `Inferred`: reasonable interpretation from artifacts.
- `Not provided`: missing evidence.
- `Not tested`: runtime/device/a11y behavior not actually tested.

If visual evidence is unavailable, mark visual judgments as plan-based rather than inspected.

## Applicability gate

Before reviewing, decide whether design review applies.

Applicable if the work includes any of:

- new or changed screen/page/component;
- user-facing flow;
- copy/microcopy;
- interaction state;
- layout/responsive behavior;
- accessibility surface;
- design-system decision.

If none apply, output: `No UI/user-facing design scope detected; design review not applicable.`

## Step 0 — Design authority and completeness rating

Rate overall design completeness from 0-10.

Use this interpretation:

- `0-2`: UI/user experience barely specified.
- `3-4`: rough direction exists, many implementer guesses remain.
- `5-6`: core flow exists, but important states or responsive/a11y details are missing.
- `7-8`: mostly buildable, a few decisions remain.
- `9-10`: implementer can build without inventing design behavior.

Also state:

- does a design system or visual authority exist?
- if yes, what should be followed?
- if no, what design decisions are currently unowned?

Hard rule: if visual tokens, component patterns, or interaction rules are unresolved, say so directly. Do not pretend design authority exists.

## Visual evidence gate

If judging visual/layout readiness, require at least one visual artifact: screenshot, prototype, mockup, recording, live screen inspection, or sufficiently specific design-system reference.

If none is available, do not give `CLEAR` for visual readiness. Mark the review as plan-based and list the visual evidence needed before build/ship confidence can be high.

## Review pass 1 — User flow and information architecture

Check whether the core journey is obvious:

- entry point;
- primary action;
- next step;
- success moment;
- escape/cancel/back path;
- first-time and returning-user behavior;
- what the user sees first, second, and third.

Flag crowded layouts, competing CTAs, weak grouping, unclear navigation, and screens that make the user infer the next action.

## Review pass 2 — Interaction states

Check loading, empty, error, success, partial, disabled, selected, validation, permission-denied, and recovery states.

For each important feature, require a state table:

| Feature | Loading | Empty | Error | Success | Partial/disabled |
|---|---|---|---|---|---|
|  | what user sees | what user sees | what user sees | what user sees | what user sees |

Describe what the user sees, not just what the system does.

## Review pass 3 — Empty/error/loading quality

Treat broken and empty states as real product moments.

Check:

- empty state explains context;
- empty state offers a useful next action when appropriate;
- errors name the problem and recovery path;
- loading state sets expectation;
- partial data does not look like failure;
- destructive or irreversible actions require enough clarity.

## Review pass 4 — Accessibility

Check where relevant:

- keyboard access;
- focus order;
- focus visible state;
- semantic structure and landmarks;
- screen-reader labels;
- form error association;
- contrast;
- touch target size;
- reduced motion;
- color-not-only signaling.

If you cannot actually test accessibility, say `not tested` and review only the specification.

## Review pass 5 — Responsive behavior

Do not accept “it stacks on mobile” as a complete spec.

Check:

- mobile, tablet, desktop behavior;
- narrow width layout;
- long labels/names/content;
- overflow;
- touch vs pointer interactions;
- density and readability;
- viewport-specific navigation.

## Review pass 6 — Copy and microcopy

Check labels, helper text, errors, headings, button text, confirmation language, trust/safety copy, and onboarding hints.

Flag vague copy such as:

- `Submit` when action-specific text is needed;
- `Error occurred` without recovery guidance;
- `No data` without context;
- generic onboarding that does not explain why the user is here.

## Review pass 7 — AI-slop / generic-design risk

Look for generic or unearned patterns:

- anonymous card grids;
- interchangeable hero copy;
- icons without information;
- “clean modern dashboard” with no hierarchy;
- decorative gradients that do not support meaning;
- UI that could belong to any product.

Do not demand novelty for its own sake. Demand specificity to the user, task, and trust context.

## Per-pass scoring rule

For any pass below `7/10`, state what would make it `10/10` and name the decision, artifact, or specification needed. Do not merely say the pass is weak.

## Design decision gate

Before declaring readiness, list decisions that implementation must not invent.

```markdown
## Design Decision Gate

Blocking design decisions:
1. ___ — why it blocks build/readiness: ___

Design authority status: explicit / partial / missing
Visual evidence status: inspected / plan-based only / missing
State coverage status: complete / partial / missing
Responsive/a11y status: specified / partial / not specified
```

If the implementer must invent information hierarchy, states, responsive behavior, or design tokens, verdict cannot be `CLEAR`.

## Output

Produce:

# GStack Lite Design Review

## Verdict
`CLEAR` / `CLEAR WITH DESIGN FIXES` / `BLOCKED`

Verdict criteria:

- `CLEAR`: design is specific enough to build or ship without major guessing, and required visual/layout claims have adequate evidence.
- `CLEAR WITH DESIGN FIXES`: direction is sound, but specific design decisions must be added or corrected.
- `BLOCKED`: missing design authority, unresolved flow/states, accessibility/responsive gaps, or absent visuals make readiness unsafe.

## Evidence ledger

| Type | Notes |
|---|---|
| Inspected |  |
| Plan-stated |  |
| Inferred |  |
| Not provided |  |
| Not tested |  |

## Design completeness score

Initial score: `__/10`

What would make it a 10:

## Visual evidence status

| Screen / flow | Evidence used | Confidence | Notes |
|---|---|---|---|
|  | screenshot / prototype / mockup / recording / live screen / plan only | high / medium / low |  |

## Design authority status

## User flow and information architecture

## Visual hierarchy review

## Interaction states review

## Empty/loading/error states

## Accessibility review

## Responsive behaviour review

## Copy and microcopy

## AI-slop / generic-design risk

## Design-system gaps

## Implementation risks

## Required design decisions before build

These block readiness.

## Recommended design changes

Separate must-fix from polish.

## Design Decision Gate

## Final design readiness

State whether the plan/screen is ready to implement, ready to ship, needs design-system authority, needs visual exploration, or needs another pass.
