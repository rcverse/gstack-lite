# gstack-lite

Portable, low-token review skills distilled from the public GStack methodology.

This package is not GStack. It does not include the GStack runtime, browser daemon, telemetry, dashboards, local `~/.gstack` state, update checks, or proactive routing. It keeps the useful review discipline in small Markdown skills that can be copied into Claude Code or used as standalone review prompts.

The governing standard is `DISTILLATION_STANDARD.md`: preserve methodology and operational pressure, remove runtime machinery, keep each skill project-agnostic.

Current scope: this initial pack is production-usable for idea shaping, strategic/scope review, design readiness, engineering readiness, and evidence-based QA. It is not yet a complete pre-merge or release workflow pack until code-review and release-check skills are added.

## Included skills

| Skill | Use for | Core question |
|---|---|---|
| `gstack-lite-office-hours` | early idea shaping before a PRD or plan exists | What is the real problem, user/operator, evidence, and narrowest useful wedge? |
| `gstack-lite-ceo-review` | PRDs, feature plans, roadmap/scope decisions | Are we solving the right problem at the right scope? |
| `gstack-lite-eng-review` | implementation plans, architecture, build readiness | Is this plan buildable, testable, and safe to implement? |
| `gstack-lite-design-review` | UI/UX plans or implemented screens | Is the user experience specified and intentional enough to build or ship? |
| `gstack-lite-qa-review` | built features, demos, release checks | Did the critical user journeys actually work when inspected or tested? |

Backlog ideas are documented in `DESIGN_NOTES.md`: code review, debug investigation, retro, and release check.

Current limitation: this initial pack does not yet include lite code review, debug investigation, or release check. For pre-merge and release workflows, use the current skills as planning/design/engineering/QA gates until those backlog skills are added.

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

### Generic repo usage

Use the `SKILL.md` files as review prompts. They are written to run without any GStack binaries or state.

## Usage pattern

1. Give the reviewer the relevant authority files: PRD, plan, architecture notes, design brief, screenshots, demo URL, test notes, or diff.
2. Invoke the appropriate lite skill.
3. Ask for a report file using `templates/review-report-template.md` or `templates/qa-report-template.md` when you want a durable artifact.
4. Treat `BLOCKED` or `DO NOT SHIP` as a real stop, not a vibe.

## Suggested sequence

For a new idea:

1. `gstack-lite-office-hours`
2. `gstack-lite-ceo-review`
3. `gstack-lite-design-review` if UI/UX exists
4. `gstack-lite-eng-review`
5. Implement using your chosen harness
6. `gstack-lite-qa-review`

For an already-written plan:

1. `gstack-lite-ceo-review` if scope or problem fit is still uncertain
2. `gstack-lite-design-review` if design decisions are involved
3. `gstack-lite-eng-review` before implementation

For an already-built feature:

1. `gstack-lite-qa-review`
2. optionally future `gstack-lite-code-review` when implemented

## Quality boundary

These skills review and report by default. They do not modify files unless the user explicitly asks. That is intentional: the lite pack is a portable methodology layer, not an autonomous build system.

Each skill should preserve operational pressure through evidence ledgers, alternatives, decision gates, failure maps, verdict criteria, and explicit NOT-in-scope handling. If a skill becomes a generic checklist, it has failed the distillation standard.
