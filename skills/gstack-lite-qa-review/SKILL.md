---
name: gstack-lite-qa-review
description: Evidence-based QA review for built features, demos, staging URLs, screenshots, or user flows. Use after implementation to test critical paths, classify issues, record reproduction steps, and decide whether to ship.
---

# GStack Lite QA Review

You are reviewing a built thing, not imagining one. QA findings must be evidence-based. If you did not run, inspect, click, or otherwise verify something, mark it as `not tested`.

Do not modify files unless the user explicitly asks. This lite QA skill reports by default; it does not auto-fix.

## Inputs

Use any available:

- staging URL, local URL, demo, screenshots, recording, build artifact, or manual test notes;
- feature spec, acceptance criteria, PRD, or implementation summary;
- browser/device/environment details;
- auth state and test accounts if provided;
- known regressions or areas of concern.

If no runnable or inspectable artifact exists, produce a QA plan rather than a QA verdict and mark the verdict `DO NOT SHIP — not tested`.

## Review sequence

### 1. Environment

Record what was tested:

- URL/build/version/commit if known;
- browser/device/viewport if known;
- account/auth state if relevant;
- date/time;
- limitations.

### 2. Critical path

Identify and test or inspect the core user journey. Focus on what must work for the feature to be useful.

### 3. Test matrix

Cover as relevant:

- happy path;
- first-time/empty state;
- invalid input;
- slow/loading state;
- error/recovery state;
- permissions/auth state;
- mobile/responsive behavior;
- accessibility basics;
- regression-sensitive adjacent flows.

### 4. Findings

Each finding must include:

- severity: `P0`, `P1`, `P2`, or `P3`;
- type: `bug`, `usability`, `accessibility`, `polish`, or `performance`;
- reproduction steps;
- expected behavior;
- actual behavior;
- evidence reviewed;
- suggested fix.

Severity guide:

- `P0`: blocks core use, data loss, security/privacy issue, or crash.
- `P1`: major journey broken or severe confusion with no good workaround.
- `P2`: meaningful bug or usability problem with workaround.
- `P3`: polish, copy, minor accessibility, or low-risk visual issue.

### 5. Ship recommendation

Base the recommendation on evidence, not optimism.

- `SHIP`: no P0/P1, no serious unknowns, core path verified.
- `SHIP WITH MINOR ISSUES`: only P2/P3 remain and they are acceptable for this release.
- `DO NOT SHIP`: any P0/P1, untested core path, or major unresolved risk.

## Output

Produce:

# GStack Lite QA Review

## Verdict
`SHIP` / `SHIP WITH MINOR ISSUES` / `DO NOT SHIP`

## Environment

## Critical path tested

Say what was tested and what was not tested.

## Test matrix

| Area | Result | Evidence / notes |
|---|---|---|
| Happy path | pass/fail/not tested |  |
| Empty state | pass/fail/not tested |  |
| Error state | pass/fail/not tested |  |
| Responsive | pass/fail/not tested |  |
| Accessibility basics | pass/fail/not tested |  |
| Regression-sensitive flows | pass/fail/not tested |  |

## Findings

For each finding:

### Finding N — short title

- Severity: `P0` / `P1` / `P2` / `P3`
- Type: `bug` / `usability` / `accessibility` / `polish` / `performance`
- Reproduction steps:
- Expected:
- Actual:
- Evidence:
- Suggested fix:

## Edge cases checked

## Accessibility checks

## Regression risk

## Final ship recommendation

State the exact condition for shipping, if not already shippable.
