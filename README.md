# gstack-lite

Portable, low-token methodology skills distilled from the public GStack methodology.

## What you get

Seven Markdown skills for AI-assisted work:

- shape rough ideas before a PRD exists;
- review product scope and strategic fit;
- review implementation plans before coding;
- explore multiple visual directions;
- create static HTML references, lightweight clickable prototypes, or handoff artifacts;
- review UI/UX readiness;
- run evidence-based QA on built features or demos.

Use them as Claude Code skills or as plain prompts in any capable agent.

## What this is not

This package is not GStack. It does not include the GStack runtime, browser daemon, telemetry, dashboards, local `~/.gstack` state, update checks, proactive routing, or auto-ship behavior.

The goal is to keep the useful review and artifact-generation discipline in small Markdown skills that can travel between projects.

## Included skills

| Skill | Use for | Core question |
|---|---|---|
| `gstack-lite-office-hours` | early idea shaping before a PRD or plan exists | What is the real problem, user/operator, evidence, and narrowest useful wedge? |
| `gstack-lite-ceo-review` | PRDs, feature plans, roadmap/scope decisions | Are we solving the right problem at the right scope? |
| `gstack-lite-eng-review` | implementation plans, architecture, build readiness | Is this plan buildable, testable, and safe to implement? |
| `gstack-lite-design-shotgun` | standalone visual exploration, direction briefs, and generation prompts | Which distinct visual directions are grounded enough to choose or refine? |
| `gstack-lite-design-html` | standalone static HTML reference, lightweight clickable prototype, or implementation handoff | What should the reference/prototype express, and what is not production? |
| `gstack-lite-design-review` | standalone UI/UX plan or implemented-screen audit | Is the user experience specified and intentional enough to build or ship? |
| `gstack-lite-qa-review` | built features, demos, release checks | Did the critical user journeys actually work when inspected or tested? |

Each skill is independently invocable. Suggested sequences are examples, not required pipelines. Skills may recommend each other as optional next steps when their own output reveals a need, but no skill depends on another by default.

Current limitation: this pack does not yet include lite code review, debug investigation, or release check. For pre-merge and release workflows, use the current skills as planning/design/engineering/QA gates until those skills are added.

## Quick use

1. Open the relevant `skills/<skill-name>/SKILL.md`.
2. Give your agent that skill plus the relevant PRD, plan, design brief, screenshot, prototype, demo URL, test notes, or diff.
3. Ask for the skill's output format.

Example:

```text
Use `gstack-lite-eng-review` to review this implementation plan.
Mark repo-dependent claims as not verified.
Do not edit files.
```

## Install

### Personal Claude Code install

Copy each skill directory into your personal skills folder:

```bash
mkdir -p ~/.claude/skills
cp -R skills/gstack-lite-* ~/.claude/skills/
```

### Project Claude Code install

Copy into the project:

```bash
mkdir -p .claude/skills
cp -R skills/gstack-lite-* .claude/skills/
git add .claude/skills
git commit -m "chore: add gstack-lite review skills"
```

### Generic prompt usage

Use the `SKILL.md` files as review or artifact-generation prompts. They are written to run without any GStack binaries or state.

## Usage pattern

1. Give the agent the relevant authority files: PRD, plan, architecture notes, design brief, screenshots, demo URL, test notes, or diff.
2. Invoke the appropriate lite skill directly.
3. Ask for a report file using `templates/review-report-template.md` or `templates/qa-report-template.md` when you want a durable artifact.
4. Treat `BLOCKED` or `DO NOT SHIP` as a real stop, not a vibe.

## Design usage guidance

- `gstack-lite-design-shotgun` is for standalone visual exploration: variant briefs, design hypotheses, generation prompts, shortlist/synthesis, and handoff notes.
- `gstack-lite-design-html` is for standalone static reference/prototype/handoff generation: it preserves authority, scopes visual references, and separates prototype/reference output from production implementation.
- `gstack-lite-design-review` is for standalone audit/readiness review: it critiques plans, screenshots, prototypes, or implemented screens.

These design skills may compose, but do not depend on one another. For example, a selected shotgun direction can feed an HTML reference, and an HTML reference can later be reviewed, but either skill can also be used directly from authority docs, screenshots, or user notes.

## Optional workflow examples

For a new idea:

1. `gstack-lite-office-hours`
2. `gstack-lite-ceo-review`
3. `gstack-lite-design-shotgun` if visual direction is unresolved
4. `gstack-lite-design-html` if a static reference/prototype/handoff artifact is useful
5. `gstack-lite-design-review` if UI/UX readiness needs critique
6. `gstack-lite-eng-review`
7. Implement using your chosen harness
8. `gstack-lite-qa-review`

For an already-written plan:

1. `gstack-lite-ceo-review` if scope or problem fit is still uncertain
2. `gstack-lite-design-shotgun`, `gstack-lite-design-html`, or `gstack-lite-design-review` only when the design problem calls for that specific action
3. `gstack-lite-eng-review` before implementation

For an already-built feature:

1. `gstack-lite-qa-review`
2. optionally future `gstack-lite-code-review` when implemented

## Repo map

- `skills/` — the portable skills.
- `templates/` — optional report templates.
- `examples/` — example outputs.
- `DISTILLATION_STANDARD.md` — durable quality standard for skills.
- `SKILL_WORKFLOW.md` — maintainer workflow for drafting, revising, and smoke-testing skills.
- `SOURCE_MAP.md` — provenance map from original GStack methodology to this lite pack.
- `NOTICE.md` — attribution notice.

## Maintainer workflow

Use `SKILL_WORKFLOW.md` when drafting a new skill, revising an existing skill, or smoke-testing whether a skill can run end-to-end as a standalone prompt. Keep durable standards in `DISTILLATION_STANDARD.md`; keep the practical drafting/testing procedure in `SKILL_WORKFLOW.md`.

## Quality boundary

These skills review, specify, or generate handoff/reference artifacts by default. They do not modify files unless the user explicitly asks. That is intentional: the lite pack is a portable methodology layer, not an autonomous build system.

Each skill should preserve operational pressure through evidence ledgers, alternatives, decision gates, failure maps, verdict criteria, and explicit NOT-in-scope handling. If a skill becomes a generic checklist, it has failed the distillation standard.
