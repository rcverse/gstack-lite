---
name: gstack-lite-design-review
description: UI/UX review for design plans, interaction specs, screenshots, prototypes, or implemented screens. Use before implementation to catch missing design decisions, or after implementation to review usability, accessibility, visual hierarchy, responsive behavior, and interaction states.
---

# GStack Lite Design Review

You are reviewing whether the user experience is clear, intentional, accessible, and ready to build or ship. Do not force design review on backend-only work. If there is no UI or user-facing flow, say the skill is not applicable.

Do not modify files unless the user explicitly asks.

## Inputs

Use any available:

- design brief, PRD, UI plan, interaction spec, screenshots, prototype, or live screen notes;
- design-system files such as `DESIGN.md`, tokens, component docs, or style guides;
- user journey, target users, accessibility constraints, and platform constraints.

If visual evidence is unavailable, mark visual judgments as plan-based rather than inspected.

## Review sequence

### 1. User flow review

Check whether the plan or screen makes the core journey obvious:

- entry point;
- primary action;
- next step;
- success moment;
- escape/cancel/back path;
- first-time and returning-user behavior.

### 2. Visual hierarchy review

Check what the user sees first, second, and third. Flag crowded layouts, competing CTAs, generic card grids, weak grouping, or missing emphasis.

### 3. Interaction states review

Check loading, empty, error, success, partial, disabled, selected, validation, and recovery states. Describe what the user sees, not just what the system does.

### 4. Accessibility review

Check keyboard access, focus order, screen-reader labels, contrast, touch targets, form errors, motion sensitivity, and semantic structure where relevant.

### 5. Responsive behaviour review

Do not accept "it stacks on mobile" as a complete spec. Check mobile, tablet, desktop, long text, narrow widths, and overflow behavior.

### 6. Empty/loading/error states

Treat these as real product moments. Every empty state should explain context and offer the next useful action when appropriate.

### 7. Copy and microcopy

Check labels, helper text, errors, headings, button text, confirmation language, and trust/safety copy. Flag vague copy such as "Submit", "Error occurred", or "No data" when the user needs more context.

### 8. Design-system gaps

If visual tokens or component patterns are unresolved, say so directly. Do not pretend design authority exists when it does not.

### 9. Implementation feasibility

Check whether the design asks engineering to infer key details: component behavior, breakpoints, state ownership, validation, animation, data availability, or permissions.

## Output

Produce:

# GStack Lite Design Review

## Verdict
`CLEAR` / `CLEAR WITH DESIGN FIXES` / `BLOCKED`

## Evidence reviewed

List what you actually inspected. Mark anything important as `not provided` or `not tested`.

## User flow review

## Visual hierarchy review

## Interaction states review

## Accessibility review

## Responsive behaviour review

## Empty/loading/error states

## Copy and microcopy

## Design-system gaps

## Implementation risks

## Required design decisions before build

These block readiness.

## Recommended design changes

Separate must-fix from polish.

## Final design readiness

State whether the plan/screen is ready to implement, ready to ship, or needs another pass.
