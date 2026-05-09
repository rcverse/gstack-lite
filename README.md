# gstack-lite

Portable, low-token review skills distilled from the public GStack methodology.

This package is not GStack. It does not include the GStack runtime, browser daemon, telemetry, dashboards, local `~/.gstack` state, update checks, or proactive routing. It keeps the useful review discipline in small Markdown skills that can be copied into Claude Code or used as standalone review prompts.

## Included skills

| Skill | Use for | Core question |
|---|---|---|
| `gstack-lite-ceo-review` | PRDs, feature plans, roadmap/scope decisions | Are we solving the right problem at the right scope? |
| `gstack-lite-eng-review` | implementation plans, architecture, build readiness | Is this plan buildable, testable, and safe to implement? |
| `gstack-lite-design-review` | UI/UX plans or implemented screens | Is the user experience specified and intentional enough to build or ship? |
| `gstack-lite-qa-review` | built features, demos, release checks | Did the critical user journeys actually work when inspected or tested? |

Backlog ideas are documented in `DESIGN_NOTES.md`: code review, debug investigation, retro, and release check.

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
3. Ask for a report file using `templates/review-report-template.md` or `templates/qa-report-template.md`.
4. Treat `BLOCKED` or `DO NOT SHIP` as a real stop, not a vibe.

## Quality boundary

These skills review and report by default. They do not modify files unless the user explicitly asks. That is intentional: the lite pack is a portable methodology layer, not an autonomous build system.
