# Example — QA Review

This example shows the expected level of evidence in `gstack-lite-qa-review`.

## Scenario

A user asks whether a newly implemented saved-search feature is ready to ship.

## Example output excerpt

```markdown
# GStack Lite QA Review

## Verdict
DO NOT SHIP

## Evidence ledger

| Type | Notes |
|---|---|
| Tested | Happy path for creating and re-running a saved search in Chrome desktop |
| Inspected | Screenshot of empty saved-search panel |
| Reported | User says backend tests passed; not independently verified |
| Not tested | Mobile viewport, keyboard-only operation, expired auth |
| Blocked | No test account with team permissions |

## Environment

- URL/build/commit: staging URL, commit unknown
- Browser/device/viewport: Chrome desktop, 1440px
- Account/auth state: logged-in test user
- Limitations: no mobile or team-permission test account

## Critical path tested

Creating a saved search succeeded, but re-running it after changing filters loaded stale filter labels. The core journey is partially broken.

## Test matrix

| Area | Result | Evidence / notes |
|---|---|---|
| Happy path | partial | creation works; re-run has stale label issue |
| Empty state | fail | empty panel says "No data" with no next action |
| Invalid input | not tested | no direct route to invalid saved query supplied |
| Loading state | not tested | response too fast to observe loading behavior |
| Error/recovery state | fail | deleted filter creates generic error toast |
| Permissions/auth | blocked | no team-permission account |
| Responsive behavior | not tested | desktop only |
| Accessibility basics | partial | tab order works; screen-reader labels not tested |
| Regression-sensitive flows | partial | normal unsaved search still works |

## Findings

### Finding 1 — Saved search can reload stale filter labels

- Severity: P1
- Type: bug
- Reproduction steps:
  1. Run a search with filter `Status = Draft`.
  2. Save the search.
  3. Change available status filters so `Draft` is no longer valid.
  4. Re-run the saved search.
- Expected: user sees a clear recovery message and can edit or remove the stale filter.
- Actual: UI shows stale `Draft` label and results do not match visible filters.
- Evidence: observed on staging during critical-path test.
- Suggested fix: validate saved filters against current filter schema before rendering.
- Retest condition: re-run saved search with removed filter; verify recovery state.

### Finding 2 — Empty state is not actionable

- Severity: P2
- Type: usability
- Reproduction steps:
  1. Open saved-search panel with no saved searches.
- Expected: empty state explains that saved searches appear after running and saving a query.
- Actual: panel says `No data`.
- Evidence: inspected empty panel screenshot.
- Suggested fix: replace with contextual copy and primary action.
- Retest condition: new account opens panel and sees actionable empty state.

## Final ship recommendation

Do not ship until Finding 1 is fixed and retested. Finding 2 can ship later only if the team accepts the onboarding friction.
```
