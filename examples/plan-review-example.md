# Example — Plan Review Flow

This example shows how the lite skills are intended to be chained without requiring GStack.

## Scenario

A user has a plan for adding saved searches to an existing web app.

## Step 1 — Office hours, if the idea is still rough

Use `gstack-lite-office-hours` if the plan does not yet identify the real user/operator, status quo, and narrowest useful wedge.

Expected output:

- evidence ledger;
- problem statement;
- status quo;
- narrowest useful wedge;
- alternatives;
- recommendation.

## Step 2 — CEO review

Use `gstack-lite-ceo-review` when the plan exists but scope may be wrong.

Example excerpt:

```markdown
## Verdict
CLEAR WITH CHANGES

## Mode
REDUCE_SCOPE

## One-line judgment
Saved searches are worth building, but the current plan overreaches into alerts, folders, and team sharing before proving repeated-search value.

## Alternatives considered

### A — Minimal viable scope
Save a named query and let the user re-run it.

### B — Proposed / balanced scope
Save, rename, delete, and re-run saved searches with owner-only visibility.

### C — Stronger or lateral scope
Saved searches plus alerting when new results appear.

## Recommendation
Choose B. It proves the core repeated-workflow value without taking on notification semantics or team permission rules.

## What is NOT in scope
- Alerts: changes the product from retrieval to monitoring.
- Team sharing: needs permission design not required for the first wedge.
- Folders: premature until users accumulate enough saved searches.
```

## Step 3 — Design review, if UI is involved

Use `gstack-lite-design-review` if the feature changes UI.

Example excerpt:

```markdown
## Design completeness score
Initial score: 6/10

What would make it a 10:
- empty state for no saved searches;
- error state when a saved query no longer maps to valid filters;
- mobile behavior for long saved-search names;
- microcopy for save/delete confirmation.

## Required design decisions before build
1. Where does "Save search" appear after a search is run?
2. What happens when a saved search references a removed filter?
3. Can saved-search names be edited inline or only through a menu?
```

## Step 4 — Engineering review

Use `gstack-lite-eng-review` before implementation.

Example excerpt:

```markdown
## What already exists
The existing search route and filter serializer should be reused. The plan should not create a parallel query format.

## Failure map

| Path / component | What can go wrong | Visibility | Current mitigation | Test coverage | Gap |
|---|---|---|---|---|---|
| Load saved search | stored query references deleted filter | user-visible error needed | none stated | none | add validation and recovery copy |
| Save current search | duplicate name | unknown | none stated | none | define naming behavior |

## Required plan edits
1. Define saved-search object shape.
2. Reuse existing filter serialization.
3. Add tests for malformed saved query payloads.
4. Add migration and rollback notes.
```

## Result

Implementation should start only after the required CEO/design/engineering edits are reflected in the plan.
